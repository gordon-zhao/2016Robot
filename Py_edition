try:
  import cv2
except:
	print 'The openCV is not installed right'

import numpy

capture=cv2.VideoCapture(0)

def read_image():
	_,frame=capture.read()
	return frame
	
def image_processing():
	_,frame=capture.read()
	hsv_frame=cv2.cvtColor(frame, cv2.COLOR_BGR2HSV)
	lower_grey, upper_grey=numpy.array([,,]),numpy.array([,,])   #Check the range of the grey of the ball
	res=cv2.bitwise_and(frame,frame, mask=cv2.inRange(hsv, lower_grey, upper_grey))   #Filter. Only left the specific grey colored part
	#Smooth edge
	img = cv2.medianBlur(res,5)
	circles = cv2.HoughCircles(img,cv2.HOUGH_GRADIENT,1,20,param1=50,param2=30,minRadius=0,maxRadius=0)
	# Converted to grey for drawing
	cimg = cv2.cvtColor(img,cv2.COLOR_GRAY2BGR)
	circles_plot = numpy.uint16(numpy.around(circles))
	for i in circles_plot[0,:]:
		# draw the outer circle
		cv2.circle(cimg,(i[0],i[1]),i[2],(0,255,0),2)
		# draw the center of the circle
		cv2.circle(cimg,(i[0],i[1]),2,(0,0,255),3)
	display_image()
	
def display_image():
	cv2.imshow('frame',frame)
	cv2.imshow('mask',mask)
	cv2.imshow('res',res)
	cv2.imshow('Result',cimg)
	cv2.waitKey(0)
if _name_ == "_main_"
	image_processing()

	cv2.destroyAllWindows()
	
