# codingTest
Coding tests

https://programmers.co.kr/learn/courses/30/parts/12077
https://programmers.co.kr/learn/courses/30/lessons/42576

1-1. Java
```java
  import java.util.HashMap;
  import java.util.Arrays;

  class Main {

    public static void main (String[] args) {

      String[] p1 = {"leo", "kiki", "eden"};
      String[] c1 = {"eden", "kiki"};
      System.out.println(Arrays.toString(p1));
      System.out.println(Arrays.toString(c1));
      System.out.println(solution(p1, c1));

      String[] p2 = {"marina", "josipa", "nikola", "vinko", "filipa"};
      String[] c2 = {"josipa", "filipa", "marina", "nikola"};
      System.out.println(Arrays.toString(p2));
      System.out.println(Arrays.toString(c2));
      System.out.println(solution(p2, c2));

      String[] p3 = {"mislav", "stanko", "mislav", "ana"};
      String[] c3 = {"stanko", "ana", "mislav"};
      System.out.println(Arrays.toString(p3));
      System.out.println(Arrays.toString(c3));
      System.out.println(solution(p3, c3));
    }

    public static String solution(String[] participiant, String[] completion) {
      String answer = "";
      HashMap<String, Integer> hm = new HashMap<String, Integer>();
      for(String p : participiant) {
        hm.put(p, hm.getOrDefault(p, 0) + 1);
      }
      for(String c : completion) {
        hm.put(c, hm.get(c) - 1);
      }
      for(String key : hm.keySet()) {
        if(hm.get(key) != 0) {
          answer = key;
          break;
        }
      }

      return answer;
    }
  }
```
1-2. Python3
```python
  def solution(participant, completion) :
    #print("p:", participant)
    #print("c:", completion)
    answer = {}
    for p in participant :
      answer[p] = answer.get(p, 0) + 1
    for c in completion :
      answer[c] -= 1
    #print(answer)
    for a in answer :
      if answer[a] : 
        return a


  p1 = ["leo", "kiki", "eden"]
  c1 = ["eden", "kiki"]
  print(solution(p1, c1))

  p2 = ["marina", "josipa", "nikola", "vinko", "filipa"]
  c2 = ["josipa", "filipa", "marina", "nikola"]
  print(solution(p2, c2))

  p3 = ["mislav", "stanko", "mislav", "ana"]
  c3 = ["stanko", "ana", "mislav"]
  print(solution(p3, c3))
```
