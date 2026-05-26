
participació política

El objetivo de este trabajo es analizar el nivel de participación política que tienen las personas.

Código que usé para generar el trabajo
Primero cargué las librerías necesarias

library(dplyr)

library(ggplot2)

library(ggcorrplot)

Datos para la data.frame
datos <- data.frame(

Participacion_politica = c(8,5,5,4,2,9,4,8,3,5,1,8,5,1,4,2,5,6,8,3,4,7,3),

Actividad_politica = c(10,8,7,1,3,10,6,8,1,5,1,6,7,6,7,3,10,5,7,4,5,7,5),

Interes_politico = c(10,5,8,1,3,10,3,5,1,5,1,8,8,6,3,4,10,5,8,6,6,7,6),

Confianza_gobierno = c(7,5,4,3,1,6,1,1,5,1,2,9,4,2,4,9,9,8,1,7,1,6,2)

)

Limpieza de datos
corr_parti <- cor(datos, use = "pairwise.complete.obs") %>% round(2)


  Ver datos limpios
glimpse(corr_parti)

Matriz de correlación
----------------------------------------------------------
Calculamos correlación de Pearson

cor(datos$Participacion_politica, datos$Confianza_gobierno, method = "pearson")


Visualización con ggcorrplot

ggcorrplot(corr_parti, type = "lower", lab = TRUE, show.legend = TRUE) +
  ggtitle("Matriz de correlación (participación política y confianza en el gobierno)") + theme_minimal()


Gráfico de dispersión

grafica <- ggplot(datos, aes(x=Confianza_gobierno, y=Participacion_politica)) +
  geom_point() + geom_smooth(method = lm) +
  scale_x_log10() +
  labs(title = "relación entre participación politica y confianza en el gobierno",
       subtitle = paste("grafico de disperción=",round(cor(datos$Participacion_politica, datos$Confianza_gobierno), 

rafica

m1 <- lm(Participacion_politica ~ Actividad_politica + Interes_politico + Confianza_gobierno, data = datos)
summary(m1)
       
Regresion lineal
 x = "Confianza_gobierno", 
       y = "Participacion_politica",
       caption = "Fuente: Elaboración propia") +
  theme_minimal()

  

Modelo
summary(modelo)


Resultados del código


Matriz de correlación


<img width="865" height="550" alt="image" src="https://github.com/user-attachments/assets/d4584d99-6330-4cdd-a7ab-0429fdebbb93" />

La matriz de correlación muestra relaciones positivas entre las variables analizadas. La asociación más alta se observa entre actividad política e interés político (r = 0.83), lo que indica que a mayor interés en la política, mayor participación en actividades políticas. También existe una relación moderada entre participación política y actividad política (r = 0.68), así como entre participación política e interés político (r = 0.64). En contraste, la confianza en el gobierno presenta correlaciones bajas con las demás variables, lo que sugiere una relación débil con la participación y el interés político.





Gráfica del comportamiento de la variable dependiente 


<img width="865" height="550" alt="image" src="https://github.com/user-attachments/assets/fbe90e51-0ba2-4157-a95f-a101fa7555fb" />

La gráfica nos muesta que existe una relación débil negativa e cuanto al interes politico 



Regresión lineal

<img width="753" height="304" alt="image" src="https://github.com/user-attachments/assets/e8a33279-f725-439c-be59-cd1743ec7872" />



aqui se  muestra que  no se encontró evidencia estadística que respalde que las variables analizadas predigan significativamente en cuanto al interes politico derevado de las actividades en el que las personas participan en actividades políticas 













 
