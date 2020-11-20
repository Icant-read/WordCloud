# WordCloud

import java.net.URL;

import java.net.URLConnection;

import java.io.IOException;

import java.util.ArrayList;

import java.util.Scanner;

import java.util.TreeMap;

import java.net.MalformedURLException;

public class Cloud

{

	private static String str;
	private static ArrayList<String> stringstring;
	private static ArrayList<Integer> numbers;
	private static TreeMap<String, Integer> map;
	
	public Cloud() {
		str = "";
		stringstring = new ArrayList<String>();
		numbers = new ArrayList<Integer>();
		map = new TreeMap<String, Integer>();
	}
	public static void populateLists(String strong) {
		// Brianna Bowers
		str = strong;
		ArrayList<String> strings;
		strings = new ArrayList<String>();
		ArrayList<Integer> ints;
		ints = new ArrayList<Integer>();
		str=str.replaceAll("\n", " ");
		String[] d=str.split(" ");
		boolean print = false;
		String p="";
		for(int x=0;x<d.length;x++) {
			if(d[x].matches("<p>.*")) {
				print = true;
			}
			if(d[x].matches("<p><a.*")) {
				print = false;
			}
			if(print == true) {
				if(p.length()>0) {
					p+= " ";
				}
				p+=d[x];
			}
			if(d[x].matches(".*</p>")) {
				print=false;
			}
		}
		String[] pp=p.split(" ");
		for(String ppp:pp) {
			ppp = ppp.replaceAll("<.*>", "");
			ppp = ppp.replaceAll(".*<.*", "");
			ppp = ppp.replaceAll(".*>.*", "");
			ppp = ppp.replaceAll("[.?!()']", "");
			if(ppp.matches(".+")) {
				strings.add(ppp);
				ints.add(1);
			}
		}
		String h1="";
		for(int x=0;x<d.length;x++) {
			if(d[x].matches("<h1>.*")) {
				print = true;
			}
			if(print == true) {
				if(h1.length()>0) {
					h1+= " ";
				}
				h1+=d[x];
			}
			if(d[x].matches(".*</h1>")) {
				print=false;
			}
		}
		String[] a=h1.split(" ");
		for(String ppp:a) {
			ppp = ppp.replaceAll("<.*>", "");
			ppp = ppp.replaceAll(".*<.*", "");
			ppp = ppp.replaceAll(".*>.*", "");
			ppp = ppp.replaceAll("[.?!()']", "");
			if(ppp.matches(".+")) {
				strings.add(ppp);
				ints.add(10);
			}
		}
		
		String h2="";
		for(int x=0;x<d.length;x++) {
			if(d[x].matches("<h2>.*")) {
				print = true;
			}
			if(print == true) {
				if(h2.length()>0) {
					h2+= " ";
				}
				h2+=d[x];
			}
			if(d[x].matches(".*</h2>")) {
				print=false;
			}
		}
		String[] b=h2.split(" ");
		for(String ppp:b) {
			ppp = ppp.replaceAll("<.*>", "");
			ppp = ppp.replaceAll(".*<.*", "");
			ppp = ppp.replaceAll(".*>.*", "");
			ppp = ppp.replaceAll("[.?!()']", "");
			if(ppp.matches(".+")) {
				strings.add(ppp);
				ints.add(8);
			}
		}
		String h3="";
		for(int x=0;x<d.length;x++) {
			if(d[x].matches("<h3>.*")) {
				print = true;
			}
			if(print == true) {
				if(h3.length()>0) {
					h3+= " ";
				}
				h3+=d[x];
			}
			if(d[x].matches(".*</h3>")) {
				print=false;
			}
		}
		String[] c=h3.split(" ");
		for(String ppp:c) {
			ppp = ppp.replaceAll("<.*>", "");
			ppp = ppp.replaceAll(".*<.*", "");
			ppp = ppp.replaceAll(".*>.*", "");
			ppp = ppp.replaceAll("[.?!()']", "");
			if(ppp.matches(".+")) {
				strings.add(ppp);
				ints.add(6);
			}
		}
		String h4="";
		for(int x=0;x<d.length;x++) {
			if(d[x].matches("<h4>.*")) {
				print = true;
			}
			if(print == true) {
				if(h4.length()>0) {
					h4+= " ";
				}
				h4+=d[x];
			}
			if(d[x].matches(".*</h4>")) {
				print=false;
			}
		}
		String[] e=h4.split(" ");
		for(String ppp:e) {
			ppp = ppp.replaceAll("<.*>", "");
			ppp = ppp.replaceAll(".*<.*", "");
			ppp = ppp.replaceAll(".*>.*", "");
			ppp = ppp.replaceAll("[.?!()']", "");
			if(ppp.matches(".+")) {
				strings.add(ppp);
				ints.add(4);
			}
		}
		String h5="";
		for(int x=0;x<d.length;x++) {
			if(d[x].matches("<h5>.*")) {
				print = true;
			}
			if(print == true) {
				if(h5.length()>0) {
					h5+= " ";
				}
				h5+=d[x];
			}
			if(d[x].matches(".*</h5>")) {
				print=false;
			}
		}
		String[] f=h5.split(" ");
		for(String ppp:f) {
			ppp = ppp.replaceAll("<.*>", "");
			ppp = ppp.replaceAll(".*<.*", "");
			ppp = ppp.replaceAll(".*>.*", "");
			ppp = ppp.replaceAll("[.?!()']", "");
			if(ppp.matches(".+")) {
				strings.add(ppp);
				ints.add(2);
			}
		}
		String h6="";
		for(int x=0;x<d.length;x++) {
			if(d[x].matches("<h6>.*")) {
				print = true;
			}
			if(print == true) {
				if(h6.length()>0) {
					h6+= " ";
				}
				h6+=d[x];
			}
			if(d[x].matches(".*</h6>")) {
				print=false;
			}
		}
		String[] g=h6.split(" ");
		for(String ppp:g) {
			ppp = ppp.replaceAll("<.*>", "");
			ppp = ppp.replaceAll(".*<.*", "");
			ppp = ppp.replaceAll(".*>.*", "");
			ppp = ppp.replaceAll("[.?!()']", "");
			if(ppp.matches(".+")) {
				strings.add(ppp);
				ints.add(1);
			}
		}

		String title="";
		for(int x=0;x<d.length;x++) {
			if(d[x].matches("<title>.*")) {
				print = true;
			}
			if(print == true) {
				if(title.length()>0) {
					title+= " ";
				}
				title+=d[x];
			}
			if(d[x].matches(".*</title>")) {
				print=false;
			}
		}
		String[] t=title.split(" ");
		for(String ppp:t) {
			ppp = ppp.replaceAll("<.*>", "");
			ppp = ppp.replaceAll(".*<.*", "");
			ppp = ppp.replaceAll(".*>.*", "");
			ppp = ppp.replaceAll("[.?!()']", "");
			if(ppp.matches(".+")) {
				strings.add(ppp);
				ints.add(10);
			}
		}

		String li="";
		for(int x=0;x<d.length;x++) {
			if(d[x].matches("<li>.*")) {
				print = true;
			}
			if(print == true) {
				if(li.length()>0) {
					li+= " ";
				}
				li+=d[x];
			}
			if(d[x].matches(".*</li>")) {
				print=false;
			}
		}
		String[] lli=li.split(" ");
		for(String ppp:lli) {
			ppp = ppp.replaceAll("<.*>", "");
			ppp = ppp.replaceAll(".*<.*", "");
			ppp = ppp.replaceAll(".*>.*", "");
			ppp = ppp.replaceAll("[.?!()']", "");
			if(ppp.matches(".+")) {
				strings.add(ppp);
				ints.add(10);
			}
		}
		
		String href="";
		for(int x=0;x<d.length;x++) {
			if(d[x].matches(".*<a.*")) {
				print = true;
			}
			if(print == true) {
				if(href.length()>0) {
					href+= " ";
				}
				href+=d[x];
			}
			if(d[x].matches(".*</a>.*")) {
				print=false;
			}
		}
		String[] xyz=href.split(" ");
		for(String ppp:xyz) {
			ppp = ppp.replaceAll("<.*>", "");
			ppp = ppp.replaceAll(".*<.*", "");
			ppp = ppp.replaceAll(".*>", "");
			ppp = ppp.replaceAll("[.?!()']", "");
			if(ppp.matches(".+")) {
				strings.add(ppp);
				ints.add(5);
			}
		}
		//make another for <a href = "word"> word </a>
		
		for(int xx=0;xx<strings.size();xx++) {
			stringstring.add(strings.get(xx));
			numbers.add(ints.get(xx));
			//This below prints the lists, you can delete this
			//System.out.println(strings.get(xx) + " " + ints.get(xx));
		}
		//System.out.println(str);
	}
	
	public static void makeMap() {
		//Joshua Navarro
		for (int x = 0; x < stringstring.size(); x++) {
			if (!map.containsKey(stringstring.get(x))) {
				map.put(stringstring.get(x),0);
			}
			map.put(stringstring.get(x), map.get(stringstring.get(x)) + numbers.get(x));
		}
	}
	
	public void paint(Graphics window){
	//Kalen Kim
		
	setBackground(Color.white);
	window.setColor(Color.lightGray);
	ArrayList<Integer> sortHighLow = new ArrayList<Integer>();
	ArrayList<String> wordsDescend = new ArrayList<String>();
	
	for(Entry<String, Integer> entry: map.entrySet()) {
		Integer  a = entry.getValue();
		sortHighLow.add(a);
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
