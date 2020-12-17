## 알고리즘의 효율성

    성능 : '시간'과 '공간' 사용량의 효율성
          컴퓨터의 실행 속도나 메모리의 가격에 무관

### 순차탐색 vs 이분검색(Binary Search)

    순차탐색 : 정렬되지 않은 리스트에서 키 찾기
             *최악의 경우 n번의 비교수행*

    이분검색 : 정렬된 리스트에서 키 찾기
             -> 주어진 리스트 S 와 x에 대해서, 
                x를 리스트의 중앙에 위치한 원소와 비교
                x가 중앙의 원소보다 작으면 왼쪽 리스트에 대해서 이진 탐색 실행
                더이상 찾을 리스트가 없으면 알고리즘 종료
             *최악의 경우 'lgn+1'번의 비교수행*

            ''' 
            def binsearch(n, S, x):
                low = 1
                high = n
                location = 0
                while (low <= high and location == 0):
                    mid = (low + high) // 2
                    if (x == S[mid]):
                        location = mid
                    elif (x < s[mid]):
                        high = mid - 1
                    else:
                        low = mid + 1
                return location
            '''

### 피보나치 수열

    1. 재귀함수이용한 피보나치 수열 -> 시간효율이 좋지 않다. 

    '''
    def fib (n):
        if (n < 1):
            return n
        else
            return fib(n - 1) + fib(n - 2)
    '''

    2. 같은 값은 중복해서 재귀적으로 계산하지 않도록 한다 -> 시간효율은 좋으나 공간효율이 좋지 않다.

    '''
    def fib2 (n):
        f =[0] * (n + 1)
        if (n>0):
            f[1] = 1
            for i in range(2,n + 1):
                f[i] = f[i-1] +f[i - 2]
        return f[n]
    '''

    3. f[n], f[n-1], f[n-2]가 저장될 공간만 사용한다.