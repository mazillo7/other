# Конвертер
### c формата 
`21.12.2012`
### в формат
`2100
1200
2012 `

Единственная проблема: Arduino IDE пиздит ногами за `String` в коде.

```sh 

void kk();
 
 
void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
  kk();
}

void kk() {
    int cl=0;
    int cl1=0;
    int page=0;
    char S[60] = "21.12.2012"; // 2, 5 - hlam
    char S1[9]= {S[0], S[1], S[3], S[4], S[6], S[7], S[8], S[9] };
    int stats[3][5];
    Serial.println(S);
    Serial.println(S1);
    Serial.println("==Сортируем шо==");
    for(int i=0; i<3; i++){
        for(int j=0; j<4; j++){
            stats[i][j]=S1[page] - 48; 
             Serial.print(stats[i][j]); 
            cl++;
            if(cl==2 && cl1!=2){
                stats[i][2]=0;
                stats[i][3]=0;
                cl=0;
                cl1++;
                page++;
                break;
            }
            else if(cl==2 && cl1==2){
                //
            }
            page++;
        }
         Serial.println();
    }
    Serial.println("==Вывод==");
    for(int i=0; i<3; i++){
        for(int j=0; j<4; j++){
            Serial.print(stats[i][j]);
            Serial.print(" ");
        }
         Serial.println();
    }
}
```
