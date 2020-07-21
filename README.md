#include <cs50.h>
#include <stdio.h>

// 매개변수화
float average(int length, int array[]); 

int main(void)
{
  int n = get_int("Scores length:  "); // 입력할 점수의 갯수(배열의 길이)를 사용자가 입력

  int scores[n];
  for (int i = 0; i < n; i++)
  {
    scores[i] = get_int("Score %i: ", i + 1); // for문에서 받은 length(배열의 길이)만큼 사용자가 Score(배열) 입력 (i+1 안해도됨, 사용자편의를 위함)
  }

  printf("Average: %.1f\n", average(n, scores)); // 평균의 소수점 아래 첫번째자리까지 출력, average 함수는 아래에 정의한다.
}

// 매개변수화
float average(int length, int array[]) //평균을 계산하는 함수 (length = 배열의 길이, array[] = 배열)
{
    int sum = 0; // 0차순부터
    for (int i = 0; i < length; i++) // 입력받은 length(배열의 길이)만큼 아래를 계산한다.
    {
        sum += array[i]; // sum = sum + array[i]; 와 같다. sum0부터 i까지 array(배열)들을 더해준다.
    }
    return (float) sum / (float) length; // sum을 length로 나눠준 값을 float average(int length, int array[])에 반환한다. (sum, length를 형변환 시켜 실수로 반환하도록 한다.)
}
