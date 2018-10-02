class Box
{
    private double width;
    private double height;
    private double depth;


Box(Box ob) //constructor 1: Passing an object as an argument
{
    width=ob.width;
    height=ob.height;
    depth=ob.depth;
}

Box(double w,double h,double d)  //Constructor with 3 dimensions as parameters
{
    width=w;
    height=h;
    depth=d;
}

Box() //Value already provided
{
    width=1;
    height=1;
    depth=1;
}

Box(double len) //Cube creating constructor
{
    width=height=depth=len;
}    

double volume()
{
    return width*height*depth;
}
}

class BoxWeight extends Box  //Used to add an additional attribute which is weight of the box
{
    double weight;


BoxWeight(BoxWeight ob)
{
    super(ob);
    weight=ob.weight;
}

BoxWeight(double w,double d,double h,double m)
{
    super(w,h,d);
    weight=m;
}

BoxWeight()
{
    super();
    weight=1;
}

BoxWeight(double len,double m)
{
    super(len);
    weight=m;
}
}

class Shipment extends BoxWeight  //Adds an additional attribue called shipment
{
    double cost;
    
    Shipment(Shipment ob)
    {
        super(ob);
        cost=ob.cost;
    }
    
    Shipment(double w,double h,double d,double m,double c)
    {
        super(w,h,d,m);
        cost=c;
    }
    
    Shipment()
    {
        super();
        cost=1;
    }
    
    Shipment(double len,double m,double c)
    {
        super(len,m);
        cost=c;
    }
    
    double cost()
    {
        return cost;
    }
}

public class DemoShipment
{
    public static void main(String args[])
    {
        Shipment shipment1=new Shipment(3,4,5,6,7); //Constructor have 5 attributes called
        Shipment shipment2=new Shipment(3,4,5); //Constructor having 3 attributes called
        Shipment shipment3=new Shipment(); //Costructor having no attribute called
        
        double vol,c;
        vol=shipment1.volume();
        c=shipment1.cost();
        System.out.println("Volume and cost of 1st shipment is "+vol+"  "+c);
        
        vol=shipment2.volume();
        c=shipment2.cost();
        System.out.println("Volume and cost of 1st shipment is "+vol+"  "+c);
        
        vol=shipment3.volume();
        c=shipment3.cost();
        System.out.println("Volume and cost of 1st shipment is "+vol+"  "+c);
    }
    }
