# LotteryApp
project that show the LotteryApp
import 'package:flutter/material.dart';
import 'dart:math';

void main() {
  runApp(const Myapp());
}
class Myapp extends StatefulWidget {
  const Myapp({super.key});

  @override
  State<Myapp> createState() => _MyappState();
}

class _MyappState extends State<Myapp> {
  Random random=Random(10);
  int x=0;
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          backgroundColor: Colors.blue,
          title:const  Center(child: Text('LotteryApp',style: TextStyle(fontSize: 30,),)),

        ),
        body: Column(
          mainAxisAlignment: MainAxisAlignment.center,
              crossAxisAlignment: CrossAxisAlignment.center,
              children: [
              const Center( child:Text('your winning number is 5',style: TextStyle(fontSize: 25,),),),
                const SizedBox(
                  height: 10,
                ),
                Container(
                  height: x==5? 500:250,// ternary if bool condition
                 width: 300,
                 decoration: BoxDecoration(
                  color:  x==5? Colors.teal:Colors.grey.withOpacity(.2),
                   borderRadius: BorderRadius.circular(10,),
                 ),
                 child:  Padding(
                   padding: const EdgeInsets.all(15.0),
                   child:x==5?
                   Column(
                     mainAxisAlignment: MainAxisAlignment.center,
                     crossAxisAlignment: CrossAxisAlignment.center,
                     children: [
                       const Icon(Icons.done_all,color:Colors.green,size: 35,),
                       Text('Congratulation you have win lottery your number is $x \n ',style: const TextStyle(fontSize: 15,),textAlign: TextAlign.center,),

                     ],
                   ):


                   Column(
                     mainAxisAlignment: MainAxisAlignment.center,
                     crossAxisAlignment: CrossAxisAlignment.center,
                     children: [
                      const Icon(Icons.error,color:Colors.red,size: 35,),
                       Text('Better luck next time your is $x \n try again',style: const TextStyle(fontSize: 15,),textAlign: TextAlign.center,),

                     ],
                   ),
                 )
                ),
              ],



        ),
        floatingActionButton: FloatingActionButton(
          onPressed: (){
            x=random.nextInt(6);
            print(x);
            setState(() {

            });
            print("tap");
          },
          backgroundColor: Colors.blue,
          child:const  Icon(Icons.refresh),
        ),
      ),
    );
  }
}



