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
	private static ArrayList stringstring;
	private static ArrayList numbers;
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
			System.out.println(strings.get(xx) + " " + ints.get(xx));
		}
		//System.out.println(str);
	}
	
	public static void makeMap() {
		
	}
	
	public static void paint() {
		
	}
}
