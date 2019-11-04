# Pocket Painter

A simple tool for painting based on HTML,CSS,JavaScript(canvas).
[Have a try here!](https://jiaozi1122.com/painter/ "Have a try here!")

## Overview
For this online tool, you can choose to draw a line, circle, rectangle, or free line. Also, you can clear your painter by clicking `Clear` button.

Please confirm the pics below:
![Dialog Layout](https://github.com/koshiryo/pocketPainter/blob/master/img/1.png)

## Details
#### Draw a painting
    // draw a painting
    function draw_picture(Shape,startx,starty,endx,endy){
    	switch(Shape){	
    	case 1://line
    		cxt.beginPath();
    		cxt.moveTo(startx,starty);
    		cxt.lineTo(endx,endy);
    		cxt.stroke();
    		cxt.closePath();
    		break;
    	case 2://circle
    		var temp=Math.sqrt(Math.pow((endx-startx),2)+Math.pow((endy-starty),2));
    		cxt.beginPath();
    		cxt.arc(startx,starty,temp,0,Math.PI*2,true);
    		cxt.stroke();
    		cxt.closePath();
    		break;	
    	case 3://regtangle
    		cxt.beginPath();
    		cxt.rect(startx,starty,endx-startx,endy-starty);
    		cxt.stroke();
    		cxt.closePath();
    		break;	
    	case 4://free line
    		draw_pencil();
    	}
    }
#### Draw a free line
    //draw a free line
    function draw_pencil(){
    	cxt.beginPath();
    	cxt.lineJoin="round";
    	cxt.moveTo(startX,startY);	
    	cxt.lineTo(endX,endY);	
    	cxt.stroke();
    	cxt.closePath();
    	startX=endX;
    	startY=endY;
    }

#### Clear the paintings
    //clear
    function clear(){
    	//alert
    	var reminder=confirm("The operation is irreversible!");
    	if(reminder==true){
    			cxt.clearRect(0,0,canvas.width,canvas.height);
    			endX=null;
    			shapes =[];
    	}
    }
## Authors

* **Koshi Ryo**

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

