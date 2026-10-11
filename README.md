# OOP2026
### Homework1
```java
public class Homework1 {
    public static void main(String[] args) {
        int i, j;

        for (i = 0; i < 10; i++) {
            for (j = 0; j <= i; j++) {
                System.out.print("#");
            }
            System.out.println();
        }
        System.out.println();
        
        for (i = 0; i < 10; i++) {
            for (j = 0; j < 10 - i; j++) {
                System.out.print("#");
            }
            System.out.println();
        }
        System.out.println();
        
        for (i = 0; i < 10; i++) {
            for (j = 0; j < 10 - 1 - i; j++) {
                System.out.print(" ");
            }
            for (j = 0; j <= i; j++) {
                System.out.print("#");
            }
            System.out.println();
        }
        System.out.println();

        for (i = 0; i < 10; i++) {
            for (j = 0; j < i; j++) {
                System.out.print(" ");
            }
            for (j = 0; j < 10 - i; j++) {
                System.out.print("#");
            }
            System.out.println();
        }
    }
}
```
![Alt homework11](./images/homework1.jpg)
### Homwork2
```java
public class Homework2 {
    public static void main(String[] args) {
        int i;
    	int n = 20;
        int[] fibo = new int[n];

        fibo[0] = 1;
        fibo[1] = 1;

        for (i = 2; i < n; i++) {
            fibo[i] = fibo[i - 1] + fibo[i - 2];
        }

        for (i = 0; i < n; i++) {
            System.out.print(fibo[i] + " ");
        }
        System.out.println();
    }
}
```
![Alt homework11](./images/homework2.jpg)
### Homework3
```java
public class Homework3 {
    public static void main(String[] args) {
        int i;
    	int n = 21;
        long[] fibo = new long[n];

        fibo[0] = 1;
        fibo[1] = 1;

        for (i = 2; i < n; i++) {
            fibo[i] = fibo[i - 1] + fibo[i - 2];
        }
        for (i = 1; i < n - 1; i++) {
            double ratio = (double) fibo[i + 1] / fibo[i];
            System.out.printf("%d/%d = %.6f%n", fibo[i + 1], fibo[i], ratio);
        }
    }
}
```
![Alt homework11](./images/homework3.jpg)
### Homework4
```java
public class homework4 {
    public static void main(String[] args) {
        int i, j;
    	for (i = 1; i <= 9; i++) {
            for (j = 1; j <= 9; j++) {
                System.out.printf("%d*%d=%-2d\t", j, i, j * i);
            }
            System.out.println();
        }
    }
}
```
![Alt homework11](./images/homework4.jpg)
### Homework5
```java
public class homework5 {
	public static void main(String[] args) {
		int i, n = 100, sign = 1;
		double sum = 0;
		for(i=0;i<n;i++) {
			sum += sign*1./((2.*i+1)*Math.pow(3., i));
			sign*= -1;
		}
		System.out.println(sum*Math.sqrt(12));
		}
	}
```
![Alt homework11](./images/homework5.jpg)
### Homework6
```Java
public class homework6 {
    public static void main(String[] args) {
        int n = 7;
        int[][] binomial = new int[n][n];

        for (int i = 0; i < n; i++) {
            for (int j = 0; j <= i; j++) {
                if (j == 0 || j == i) {
                    binomial[i][j] = 1;
                } else {
                    binomial[i][j] = binomial[i - 1][j - 1] + binomial[i - 1][j];
                }
            }
        }

        for (int i = 0; i < n; i++) {
            for (int j = 0; j <= i; j++) {
                System.out.print(binomial[i][j] + " ");
            }
            System.out.println();
        }
    }
}
```
![Alt homework11](./images/homework6.jpg)
### Homework7
```Java
public class homework7 {
    public static void main(String[] args) {
        int data[] = new int[20];
        
        for (int i = 0; i < 20; i++) {
            data[i] = (int)(Math.random() * 100);
        }
        
        for (int i = 0; i < data.length - 1; i++) {
            int minIndex = i;
            for (int j = i + 1; j < data.length; j++) {
                if (data[j] < data[minIndex]) {
                    minIndex = j;
                }
            }
            int temp = data[i];
            data[i] = data[minIndex];
            data[minIndex] = temp;
        }

        for (int i = 0; i < 20; i++) {
            System.out.println(data[i]);
        }
    }
}
```
![Alt homework11](./images/homework7.jpg)
### Homework8
```Java
public class homework8 {
    public static void main(String[] args) {
        int studentCount = 30; 
        int score[][] = new int[studentCount][5]; 

        for (int i = 0; i < studentCount; i++) {
            for (int j = 0; j < 4; j++) {
                score[i][j] = (int)(Math.random() * 101);
            }
        }

        System.out.println("번호\t국어\t영어\t수학\t과학\tsum");
        System.out.println("----------------------------------------");

        for (int i = 0; i < studentCount; i++) {
            int sum = 0;
            System.out.print((i + 1) + "\t");

            for (int j = 0; j < 4; j++) {
                System.out.print(score[i][j] + "\t");
                sum += score[i][j];
            }
            
            System.out.println(sum);
        }
    }
}

```
![Alt homework11](./images/homework8.jpg)
### Homework10
```Java
public class homework10 {
	public static void main(String[] args) {
		// TODO Auto-generated method stub
		int array_count, max_value, bin_size, display_scale, hist_size;
		if(args.length !=4)
			return;
		array_count = Integer.parseInt(args[0]);
		max_value = Integer.parseInt(args[1]);
		bin_size = Integer.parseInt(args[2]);
		display_scale = Integer.parseInt(args[3]);
		hist_size = max_value/bin_size;
		
		int[] arr = new int[array_count];
		int[] hist = new int[hist_size];
		for (int i=0; i<array_count; i++) {
			arr[i] = (int) (Math.random()*max_value);
		}
		for (int i=0; i<array_count; i++) {
			System.out.print(arr[i] + " ");  
		}
		System.out.println();  
		
		for (int i=0; i<array_count; i++) {
			hist[arr[i]/bin_size]++;
		}
		for (int i=0; i<hist_size; i++) {
			System.out.print(hist[i] + " ");  
		}
		System.out.println();  
		}
	}
```
![Alt homework11](./images/homework10.jpg)
### Homework11
```Java
public class hw6 {
	public static void main(String[] args) {
		// TODO Auto-generated method stub
		int array_count;
		if(args.length !=1)
			return;
		array_count = Integer.parseInt(args[0]);
		int[] arr = new int[array_count];
		for (int i=0; i<array_count; i++) {
			arr[i] = (int) (Math.random()*100);
		}
		for (int i=0; i<array_count; i++) {
			System.out.print(arr[i] + " ");  
		}
		System.out.println();
		double sum = 0;
		for (int i=0; i<array_count; i++) {
			sum+=arr[i];
		}
		System.out.printf("arithematic mean : = %f\n", sum/array_count);
		double prod = 1;
		for (int i=0; i<array_count; i++) {
			prod*=arr[i];
		}
		System.out.printf("harmonic mean : = %f\n", Math.pow(prod, (double)1./array_count));
		}
	}
```
![Alt homework11](./images/homework11.jpg)
### Homework13
```Java
public class homework13 {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        while (true) {
            String input = scanner.nextLine().trim();
            if (input.equalsIgnoreCase("exit")) break;
            
            String[] tokens = input.split("\\s+");
            double result = Double.parseDouble(tokens[0]);
            
            for (int i = 1; i < tokens.length; i += 2) {
                String op = tokens[i];
                double val = Double.parseDouble(tokens[i + 1]);
                
                switch (op) {
                    case "+": result += val; break;
                    case "-": result -= val; break;
                    case "*": result *= val; break;
                    case "/": result /= val; break;
                    case "#": result = (result + val) / 2.0; break;
                }
            }
            
            if (result == (long) result) {
                System.out.println((long) result);
            } else {
                System.out.println(result);
            }
        }
        scanner.close();
    }
}
```
![Alt homework11](./images/homework13.jpg)
### Homework14
```Java
import java.util.Scanner;

import java.util.Arrays;

class Numbers {
    int num[];

    Numbers(int num[]) {
        this.num = num;
    }

    double getTotal() {
        double sum = 0;
        for (int i = 0; i < num.length; i++) sum += num[i];
        return sum;
    }

    double getArithmaticMean() {
        return getTotal() / num.length;
    }

    double getHarmonicMean() {
        double sum = 0;
        int count = 0;
        for (int i = 0; i < num.length; i++) {
            if (num[i] != 0) {
                sum += 1.0 / num[i];
                count++;
            }
        }
        return count == 0 ? 0 : count / sum;
    }

    double getGeometricMean() {
        double logSum = 0;
        int count = 0;
        for (int i = 0; i < num.length; i++) {
            if (num[i] > 0) {
                logSum += Math.log(num[i]);
                count++;
            }
        }
        return count == 0 ? 0 : Math.exp(logSum / count);
    }   

    int getMedian() {
        sorting();
        return num[num.length / 2];
    }

    void sorting() {
        Arrays.sort(num);
    }

    void drawHistogram(int start, int end, int binCount, int scale) {
        int bin_size = (end - start) / binCount;
        int[] hist = new int[binCount];

        for (int i = 0; i < num.length; i++) {
            int idx = (num[i] - start) / bin_size;
            if (idx >= binCount) idx = binCount - 1;
            if (idx < 0) idx = 0;
            hist[idx]++;
        }

        for (int i = 0; i < binCount; i++) {
            int bStart = start + i * bin_size;
            int bEnd = bStart + bin_size - 1;
            System.out.printf("%2d~%-2d : ", bStart, bEnd);
            
            int printCount = hist[i] / scale;
            for (int j = 0; j < printCount; j++) {
                System.out.print("#");
            }
            System.out.println();
        }
    }

    void display() {
        System.out.printf("%3d :", num.length);      
        for (int i = 0; i < num.length; i++) 
            System.out.printf("%3d ", num[i]);
        System.out.println();
    }   
}

public class hw6 {
    public static void main(String[] args) {
        int size = 100;
        int data[] = new int[size];
        for (int i = 0; i < size; i++) 
            data[i] = (int)(Math.random() * 100);
        
        Numbers obj = new Numbers(data);
        obj.display();
        
        System.out.printf("Arithmetic Mean : %5.2f\n", obj.getArithmaticMean());
        System.out.printf("Geometric Mean  : %5.2f\n", obj.getGeometricMean());      
        System.out.printf("Harmonic Mean   : %5.2f\n", obj.getHarmonicMean());
        System.out.println("Median          : " + obj.getMedian());
        
        System.out.println("\n[Histogram]");
        obj.drawHistogram(0, 100, 10, 1); 
    }
}
```
![Alt homework11](./images/homework14.jpg)
