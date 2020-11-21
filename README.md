# WordCloud

import java.awt.Graphics;
import java.awt.Color;
import java.awt.Font;
import java.awt.Canvas;
import java.awt.MouseInfo;
import java.awt.Rectangle;
import java.awt.font.FontRenderContext;
import java.awt.geom.AffineTransform;
import java.util.ArrayList;
import java.util.Collections;
import java.util.Map.Entry;
import java.util.TreeMap;
public class CloudPaint extends Canvas{
	
	//Kalen Kim
	
	private static TreeMap<String, Integer> map;
	public CloudPaint (TreeMap<String, Integer> m)
	{
		map = new TreeMap<String, Integer>();
		map = m;
		setBackground(Color.WHITE);	
		
	}

	public void paint( Graphics window )
	{
		window.setColor(Color.lightGray);
		
		
		ArrayList<Integer> sortHighLow = new ArrayList<Integer>();
		ArrayList<String> wordsDescend = new ArrayList<String>();
		int xvaluetest=30;
		int yvaluetest=30;
		for(Entry<String, Integer> entry: map.entrySet()) {
			Integer  a = entry.getValue();
			sortHighLow.add(a);
			//Brianna Bowers to next break
			int first = (int) (Math.random()*200);
			int second = (int) (Math.random()*200);
			int third = (int) (Math.random() *200);
			Color col=new Color(first, second, third);
			window.setColor(col);
			int size=entry.getValue();
			if(size>50) {
				size=50;
			}
		    window.setFont(new Font("Courier New", Font.PLAIN, size)); 
			window.drawString(entry.getKey(), xvaluetest, yvaluetest);
			xvaluetest+=50;
			if(xvaluetest>570) {
				xvaluetest=0;
				yvaluetest+=20;
			}
			//This is the next break if that wasn't clear lol
		}
			
		Collections.sort(sortHighLow, Collections.reverseOrder());
			
		for(Integer i: sortHighLow) {
			for( Entry<String, Integer> entry : map.entrySet() ){
				if(entry.getValue()==i && !wordsDescend.contains(entry.getKey())) {
		           	wordsDescend.add(entry.getKey());
		           	
		        }
			}
		}		
		    
			
		int largest = 200;
		int count = 0;
		Rectangle[] rectangles;
		    
			
		ArrayList<Integer> xs = new ArrayList<Integer>();
		ArrayList<Integer> ys =new ArrayList<Integer>();
		ArrayList<Integer> width = new ArrayList<Integer>();
		ArrayList<Integer> height = new ArrayList<Integer>();
		ArrayList<Integer> fonts = new ArrayList<Integer>();
		for(String s: wordsDescend) {
		   int x = (int)(Math.random() * (700 - 100 + 1) + 100);
		   xs.add(x);
		   int y =  (int)(Math.random() * (700 - 100 + 1) + 100);
		   ys.add(y);
		    AffineTransform affinetransform = new AffineTransform();     
		    FontRenderContext frc = new FontRenderContext(affinetransform,true,true);
		    //window.setFont(new Font("Courier New", Font.PLAIN, largest-(count*13))); 
		    Font font = new Font("Courier New", Font.PLAIN, largest-(count*14));
		    fonts.add(largest-(count*14));
		    int textwidth = (int)(font.getStringBounds(s, frc).getWidth());
		    width.add(textwidth);
		    int textheight = (int)(font.getStringBounds(s, frc).getHeight());
		    height.add(textheight);
		    
		    /*
		    window.setColor(Color.DARK_GRAY);
		    window.fillRect(x, x, textwidth, textheight);
		    window.setColor(Color.LIGHT_GRAY);
		    window.drawString(s, x, x+(textheight/2));
		    */		    
		    count++;
		}

		rectangles = new Rectangle[xs.size()];

		for(int i=0; i < xs.size(); i++) {
			Rectangle temp = new Rectangle(xs.get(i), ys.get(i), width.get(i), height.get(i));
			rectangles[i]=temp;
		}

		for(int i=0; i < rectangles.length; i++) {
			for(int j = 0; j<rectangles.length; j++) {
				if(j!=i&&(rectangles[i].intersects(rectangles[j])||rectangles[i].contains(rectangles[j]))) {
			    		int z = (int)(Math.random() * (700 - 100 + 1) + 100);
			    		int y=(int)(Math.random() * (700 - 100 + 1) + 100);
			    		rectangles[i]= new Rectangle(z,y,width.get(i), height.get(i));
				}
				j=0;
			}
			xs.set(i, (int)rectangles[i].getX());
			ys.set(i, (int)rectangles[i].getY());
			window.drawRect(rectangles[i].x, rectangles[i].y, rectangles[i].width, rectangles[i].height);
			System.out.println(xs.size() + " "+ rectangles.length);
		}


		for(int x = 0; x<rectangles.length; x++) {
		    window.setFont(new Font("Courier New", Font.PLAIN, fonts.get(x))); 
			window.drawString(wordsDescend.get(x), rectangles[x].x, rectangles[x].y+rectangles[x].height);

		}
		
	}
}

