# Sort(정렬)
## Sort : 항목들을 체계적으로 정리하는 과정
          - 순서를 정하는 것
          - 분류하는 것

### 선택정렬 (Selection Sort) O(n^2)
    : 전체 원소들 중에서 기준 위치에 맞는 원소를 선택하여 자리를 교환하는 방식이다.
      
      1) 주어진 배열에서 최솟값을 찾는다.
      2) 그 최솟값을 맨 앞에 위치한 것과 바꾼다.
      3) 맨 앞의 것을 제외하고 나머지 것들을 대상으로 1) ~ 2) 과정을 반복한다.

### 버블정렬 (Bubble Sort) O(n^2)
    : 인접한 두 개의 원소를 비교하여 자리를 교환하는 방식이다.
      (한 단계가 끝나면, 가장 큰 원소 혹은 가장 작은 원소가 마지막 자리로 위치한다.)

      1) 첫 번째 원소부터 인접한 원소끼리 자리를 교환하는 과정을 반복한다. (한단계가 끝나면 가장 큰 원소 혹은 가장 작은 원소가 마지막 자리에 위치한다.)

### 삽입정렬 (Insertion Sort) O(n^2)
    : 정렬되어 있는 부분집합에 정렬할 새로운 원소의 위치를 삽입하는 방법이다.
     
       1) 2번째 인덱스부터 시작해 선택 원소와 나머지 원소를 비교한다. (선택원소가 더 크면 비교를 진행하지 않는다)
       2) 선택 원소가 작을 경우 앞에 있던 원소를 한칸 뒤로 밀고 선택원소는 그보다 한칸 더 앞에 있던 원소와 비교를 한다.

### 퀵정렬 (Quick Sort) O(n log n)
    : 피벗(pivot)을 기준으로 두 개의 부분리스트로 나누어 하나는 피벗보다 작은 값들의 부분리스트, 다른 하나는 피벗보다 큰 값들의 부분리스트로 정렬한 다음, 각 부분리스트에 대해 다시 위 처럼 재귀적으로 수행하여 정렬하는 방법이다.
      '분할 정복' 알고리즘을 기반으로 정렬되는 방식이다.
    
       1) 피벗을 기준으로 왼쪽에서부터는 피벗보다 큰 값을 찾고, 오른쪽에서부터는 피벗보다 작은 값을 찾는다.
       2) 양방향에서 두 원소를 교환하는 과정을 반복한다.
       3) 피벗을 기준으로 두개의 쪼개진 그룹을 합친다.

### 병합정렬 (Merge Sort) O(n log n)
    : 하나의 리스트를 두 개의 균등한 크기로 분할하고 분할된 부분 리스트를 정렬한 다음, 두 개의 정렬된 부분 리스트를 합하여 전체가 정렬된 리스트가 되게 하는 방법이다.
      '분할 정복' 알고리즘을 기반으로 정렬되는 방식이다.

       1) 두개의 리스트로 분할한다.
       2) 분할한 리스트를 정렬한다.
       3) 정렬된 부분의 리스트들을 하나의 리스트에 병합한다.      

### 힙정렬 (Heap Sort) O(n log n)
    : 완전 이진 트리의 일종인 힙 트리 구조를 이용하는 정렬 방법이다.
      내림차순 정렬을 위해서는 최대 힙을 구성하고 오름차순 정렬을 위해서는 최소 힙을 구성하면 된다.

       1) 주어진 배열을 힙으로 만든다. 배열에 있는 모든 숫자를 없앤다.
       2) 힙에 있는 최댓값을 차례로 배열에 넣어주면서 삭제하는 과정을 반복한다.

### 계수정렬 (Counting Sort) O(n)
    : 데이터 값을 직접 비교하지 않고, 개수를 세어 기록하고 정렬하는 방법이다.

       1) 결과 배열의 크리를 숫자의 크기 범위만큼 잡는다.
       2) 배열에 있는 숫자의 개수를 count배열의 인덱스에 맞게 저장한다.
       3) count배열의 누적합의 배열을 저장한다. (counting 배열의 값은 시작점 -1을 의미한다.)
       4) 입력 배열과 누적합 배열의 인덱스와 비교하여 결과 배열에 저장한다. 

### Arrays.sort()
    : Dual-Pivot QuickSort 사용 (InsertionSort + QuickSort)
      java.util.Arrays 클래스 sort() 메서드, 배열 자동 오름차순 정렬
      시간복잡도 평균: O(nlog(n)) 최악 : O(n^2)
      소량 데이터 처리나, 순서 규칙적인 경우 Arrays.paralleSort()보다 성능이 좋다.

### Arrays.parallelSort()
    : java.util.Arrays 클래스의 paralleSort() 메서드이다. (Merge Sort 사용)
      배열을 병렬로 정렬하는 기능 제공한다.
      대량 데이터 처리가 Arrays.sort()보다 성능이 좋다.

### Collections.sort()
    : TimSort 사용 (MergeSort + InsertSort)
      java.util.Collections 클래스 sort() 메서드(static), 리스트 자동 오름차순 정렬
      시간복잡도 평균, 최악 : O(n^2)

### Arrays.sort() vs Collections.sort() 
    : Arrays.sort()에서 사용되는 QuickSort는 배열에서 좋은 성능을 보여 속도가 Collcetions.sort() 보다 좀 더 빠르다. 
      그러나 stable이 필요한 Object에서는 Collections.sort()가 많이 쓰인다.

### Interface Comparable
    : 정렬 수행 시 기본적으로 적용되는 정렬 기준이 되는 메서드를 정의하는 인터페이스이다.
      compareTo() 메서드 작성법
        - 현재객체 < 파라미터로 넘어온 객체 : 음수 리턴
        - 현재객체 == 파라미터로 넘어온 객체 : 0 리턴
        - 현재객체 > 파라미터로 넘어온 객체 : 양수 리턴
          => 음수 또는 0이면 객체의 자리가 그대로 유지, 양수인 경우 두 객체의 자리가 바뀐다.
      사용법 : Arrays.sort(array), Collections.sort(list)



## 20220214 - 수 정렬하기 2 (백준 알고리즘 2751) 
- 입력하는 수를 오름차순으로 정렬한다.
- String 보다 StringBuffer, StringBuilder를 이용하여 속도를 줄인다. (String < StringBuffer < StringBuilder)-성능

## 20220215 - 수 정렬하기 3 (백준 알고리즘 10989)
- 입력하는 수를 오름차순으로 정렬한다.
- String 보다 StringBuffer, StringBuilder를 이용하여 속도를 줄인다. (String < StringBuffer < StringBuilder)-성능
- Arrays.sort()를 사용하였다.

## 20220216 - 생일 (백준 알고리즘 5635)
- 입력받은 이름과 생년월일 중에서 가장 나이가 적은 사람과 가장 나이가 많은 사람을 출력한다.
- SimpleDateFormat으로 생년월일을 데이터형으로 바꾼후 Comparable 인터페이스의 Collections.sort()를 사용하여 정렬한다.

## 20220217 - 숫자놀이 (백준 알고리즘 1755)
- 숫자를 숫자 단위로 하나씩 영어로 읽어들여 사전순으로 정렬후 다시 숫자로 변환하여 출력한다.
- 숫자를 맞는 영어로 바꾸고 Arrays.sort()를 사용하여 정렬 후 StringBuilder에 출력이 필요한 값을 넣어주었다.

## 20220218 - n번째 큰 수 (백준 알고리즘 2075)
- 입력한 수의 제곱한 만큼 숫자를 입력하여 숫자 들중 입력한 수만큼 큰 수를 출력한다.
- 입력한 문자열을 공백으로 잘라 배열에 넣고 정렬하여 n번째 큰 수 위치를 지정하여 출력한다.

