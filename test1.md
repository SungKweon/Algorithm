## hello



```
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
        isVisited = new int [n+1];

        for(int i=0;i<m;i++){

            String [] connections = br.readLine().split(" ");
            int start =Integer.parseInt(connections[0]);
            int end = Integer.parseInt(connections[1]);

            graph[start][end] = 1;
            graph[end][start] = 1;
        }

        dfs(v);
        System.out.println();
        Arrays.fill(isVisited,0);
        bfs(v);

    }

    // 재귀
    public static void dfs(int v){
        isVisited[v] = 1;
        System.out.print(v + " ");

        for(int i=1;i<graph.length;i++){
            if(graph[v][i]==1&&isVisited[i]==0)
                dfs(i);
        }

    }

    // 큐
    public static void bfs(int v){

        Queue<Integer> queue = new LinkedList<>();
        queue.offer(v);
        isVisited[v] = 1;

        while(!queue.isEmpty()){

            int element = queue.poll();
            System.out.print(element + " ");

            for(int i=1;i<graph.length;i++){

                if(isVisited[i] == 0 && graph[element][i] ==1){
                    queue.offer(i);
                    isVisited[i] = 1;
                }

            }
        }
    }
}
```
