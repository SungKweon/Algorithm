## hello



import java.io.*;
import java.util.*;

public class Main {

    public static int [][] graph;
    public static int [] isVisited;

    public static void main(String[] args) throws IOException {

        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));

        String [] inputs = br.readLine().split(" ");
        int n = Integer.parseInt(inputs[0]);
        int m = Integer.parseInt(inputs[1]);
        int v = Integer.parseInt(inputs[2]);

        graph = new int [n+1][n+1];
