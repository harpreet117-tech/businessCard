BusinessCard app

```kotlin

package com.example.assignment1
import android.os.Bundle
import androidx.activity.ComponentActivity
import androidx.activity.compose.setContent
import androidx.compose.foundation.Image
import androidx.compose.foundation.layout.*
import androidx.compose.material3.Surface
import androidx.compose.material3.Text
import androidx.compose.runtime.Composable
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.graphics.Color // for adding color
import androidx.compose.ui.text.font.FontWeight // for bold text
import androidx.compose.ui.res.painterResource
import androidx.compose.ui.tooling.preview.Preview
import androidx.compose.ui.unit.dp
import androidx.compose.ui.unit.sp
import androidx.compose.foundation.background // for background
import androidx.compose.foundation.border // for border
import androidx.compose.foundation.shape.CircleShape // for converting into circle
import androidx.compose.ui.layout.ContentScale // for cropping the image
import androidx.compose.ui.draw.clip //Allows clipping UI elements into shapes


class MainActivity : ComponentActivity(){
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContent{
            Surface(
                modifier = Modifier.fillMaxSize(),
            ){
                BusinessCard()
            }
        }
    }
}

@Composable fun BusinessCard(){

    Column(   // first column the very top one
        modifier = Modifier
            .fillMaxSize()
            .background(Color.Black) //For black color background
            .padding(16.dp),
            horizontalAlignment =Alignment.CenterHorizontally,
            verticalArrangement = Arrangement.SpaceBetween
){Column(
    horizontalAlignment = Alignment.CenterHorizontally,
    modifier = Modifier.padding(top = 170.dp),
){Image(
    modifier = Modifier.size(300.dp)
        .clip(CircleShape)
        .border(4.dp, Color.White, CircleShape),
        contentScale = ContentScale.Crop, // for cropping the image
        painter = painterResource(id = R.drawable.harpreet),
        contentDescription = null,



)
        Text(
            modifier = Modifier.padding(top = 15.dp),
            text = "Harpreet Singh",
            fontSize = 35.sp,
            color = Color.White,
            fontWeight = FontWeight.Bold // for bold text
)
    Text(
        modifier = Modifier.padding(top = 15.dp),
        text = "Android Developer",
        fontSize = 23.sp,
        color = Color.White,
    )
    }
        // Very bottom column
        Column(
            verticalArrangement = Arrangement.spacedBy(8.dp),
            horizontalAlignment = Alignment.CenterHorizontally,
        ){
            Information("+6158789*****")
            Information("balkarnmann140@gmail.com")
            Information("github.com/balkarn117")
        }
    }
}
        @Composable fun Information(text: String){
            Text(
                text = text,
                fontSize = 22.sp,
                color = Color.White,
            )
        }

        @Preview(showBackground = true)
        @Composable
        fun BusinessCardPreview(){
                BusinessCard()
        }



