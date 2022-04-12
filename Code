package mp1;
import java.util.*;

class Task
{
    String name;
    int priority;
    String problem;
 
    /*  Constructor  */
    public Task(String name, int priority,String problem)
    {
        this.name = name;
        this.priority = priority; 
        this.problem=problem;
    }
    /*  toString()  */
    public String toString() 
    {
        return "Patient Name : "+ name +"\nMedical Problem : "+ problem +"\nPriority : "+ priority;
    }
}
class PriorityQueue
{
     Task[] heap; 
    int heapSize, capacity;
 
    /* Constructor */
    public PriorityQueue(int capacity)
    {    
        this.capacity = capacity + 1;
        heap = new Task[this.capacity];
        heapSize = 0;
    }
public void clear()
    {
        heap = new Task[capacity];
        heapSize = 0;
    }  
public boolean isEmpty()
    {
        return heapSize == 0;
    }
    /* function to check if full */
    public boolean isFull()
    {
        return heapSize == capacity - 1;
    }
public int size()
    {
        return heapSize;
    }
public void insert(String name, int priority,String problem)
    {
        Task newJob = new Task(name, priority,problem);
 
        heap[++heapSize] = newJob;
        int pos = heapSize;
        while (pos!= 1 && newJob.priority > heap[pos/2].priority)
        {
            heap[pos] = heap[pos/2];
            pos /=2;
        }
        heap[pos] = newJob;    
    }    
 public Task remove()
    {
        int parent, child,i;
        Task item, temp;
        if (isEmpty() )
        {
            System.out.println("All Patients Discharged! No Patients in the ER.");
            return null;
        }else {
 
        item = heap[1];
        temp = heap[heapSize--];
       
        parent = 1;
        child = 2;
        i=0;
        while (child <= heapSize)
        {
            if (child < heapSize && heap[child].priority < heap[child + 1].priority)
                child++;
            if (temp.priority >= heap[child].priority)
                break;
 
            heap[parent] = heap[child];
            parent = child;
            child *= 2;
        }
        heap[parent] = temp;
        
        return item;
    } 
    }
    
void removeDups(int heapSize)
    {
 
        // Hash map which will store the
        // elements which has appeared previously.
        HashMap<Integer,Boolean> mp = new HashMap<>();
 
        for (int i = 1; i <=heapSize; ++i)
        {
            // Print the element if it is not
            // there in the hash map
            if (mp.get(heap[i].priority) == null)
                System.out.print(heap[i] + "\n ");
 
            // Insert the element in the hash map
            mp.put(heap[i].priority, true);
        }
    }
    void display()
    {
        removeDups(heapSize);
    }
 
}
 public class Main
{
    public static void main(String[] args)
    {
        Scanner scan = new Scanner(System.in);
        
        int m,n=0,u,p=0;
        char c= '\0';
        char ch= '\0';
        
        do{
            
        System.out.println("\n***********************CRITICARE HOSPITAL*********************\n");
        System.out.println("ENTER YOUR CRITICARE HOSPITAL ID :");   
        m=scan.nextInt();
        if(m==2201||m==3241||m==6754||m==4563||m==8970||m==7224||m==6547||m==5412)
        {System.out.println("Enter the Number of Beds Available in ER Today : ");
        u=scan.nextInt();
        PriorityQueue pq = new PriorityQueue(u);
       
        /*  Perform Priority Queue operations */
        do    
        {
            do{
            System.out.println("\n********************CRITICARE HOSPITAL*********************\n");
            System.out.println("1. Admit a Patient");
            System.out.println("2. Discharge a Patient");
            System.out.println("3. Check if All Beds are Empty");
            System.out.println("4. Check if All Beds are Full");
            System.out.println("5. Clear the Patient List");
            System.out.println("6. Display Total Number of Beds in ER Today");
            System.out.println("7. Display Today's Patient List");
            System.out.println("8. Display Total Number of Beds Occupied");
            int choice = scan.nextInt();            
            switch (choice) 
             {
            case 1 : 
                System.out.println("Enter Patient Name : ");
                String pn=scan.next();
                pn+=scan.nextLine();
                System.out.println("Enter Priority Number : ");
                int prn=scan.nextInt();
                System.out.println("Enter Medical Problem : ");
                String mp=scan.next();
                mp+=scan.nextLine();
                pq.insert(pn,prn,mp); 
                pq.display();
                break;                          
            case 2 : 
                System.out.println("\nPatient Discharged Successfully!\n"+ pq.remove()); 
                break;        
            case 3 : 
                System.out.println("\nEmpty Status : "+ pq.isEmpty() );
                break; 
            case 4 : 
                System.out.println("\nFull Status : "+ pq.isFull() );
                break; 
            case 5 : 
                System.out.println("\nPatient List Cleared!");
                pq.clear();
                break;    
            case 6 : 
                System.out.println("\nTotal Beds Available : "+ u );
                break;   
            case 7:
                System.out.println("\nToday's Patient List\n : " );
                pq.display();
            
                break;
            case 8:
                System.out.println("\nOccupied Beds : "+pq.size() );
                break;
            default : 
                System.out.println("Wrong Entry ");
                break;   
             }    
 
            System.out.println("\nDo You Want to Continue\n (Type Y for Yes and N for No) \n");
            ch = scan.next().charAt(0);                        
        } while (ch == 'Y'|| ch == 'y');            
        System.out.println("Do you want to shut the System?\n(Type Y for Yes and N for No) \n");
        c = scan.next().charAt(0);
        if(c == 'Y'|| c == 'y') {
        System.out.println("Thank You for Choosing Criticare Hospital. Wish you a Healthy Life!");
        }
        n=3;
        }while(c == 'N'|| c == 'n');
        }
    else
    {System.out.println("Invalid ID. Please Try Again");
    n++;
    p++;
    }
    }while(n!=3);
        scan.close();
    if(n==3 && p==3)
    System.out.println("System Blocked due to Too Many Tries. Try Again Later ");
    }
}
