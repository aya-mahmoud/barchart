# barchart



#include <iostream>
#include <fstream>
#include <string>

using namespace std;

int main()
{
    string name;
    cout<<"ENTER THE FILE NAME (NOTE: USING .svg):"<<endl;
    cin>>name;
    ofstream barchart;
    barchart.open(name);
    int x=50,y,h;

    barchart<<"<?xml version=\"1.0\" standalone=\"no\"?> <!DOCTYPE svg PUBLIC \"-//W3C//DTD SVG 1.1//EN\" \"http://www.w3.org/Graphics/SVG/1.1/DTD/svg11.dtd\"> <svg width=\"500\" height=\"500\" xmlns=\"http://www.w3.org/2000/svg\">"<<endl;

    cout<<endl<<" ENTER THE HEIGHT OF the 4 BARs (NOTE: MAXIMUM HEIGHT IS 400)"<<endl;

    for(int i=0; i<4; i++)
    {


        cin>>h;
        while (h>400 || h<0)
        {

            cout<<"INVALID ENTER ANOTHER HEIGHT 0< H <= 400"<<endl;
            cin>>h;
        }
        x+=100;
        y=499-h;
        barchart<<"<rect x=\""<<x<<"\" y=\""<<y<<"\" width=\"50\" height=\""<<h<<"\" style=\"fill:blue;\"/>"<<endl ;

    }

    barchart << "<line x1=\"100\" y1=\"60\" x2=\"100\" y2=\"500\" style=\"stroke:purple;stroke-width:2\"/>" <<endl;

    barchart << "<line x1=\"100\" y1=\"499\" x2=\"500\" y2=\"499\" style=\"stroke:purple;stroke-width:2\"/>" <<endl;

    barchart<<"</svg>";

    barchart.close();


    return 0;
}
