# Etiquetado

Es esta apartado se explorara la administracion del consumo de recursos en una cuenta de aWS mediante etiquetas. Tambien
revisara ejemplo de casos de uso frecuentes de etiquetado que utilizan AWS Config y AWS identity and Access Management(
IAM).

## ¿Que es una etiqueta?

Una etiqueta es un rótulo que se asigna a un recurso de AWS. Le permite identificarlo o categorizarlo de forma
significativa. Cada etiqueta consta de una clave y un valor, ambos definidos por el usuario.
![](.05-etiquetado_images/33076d82.png)

## Caracteristicas

![](.05-etiquetado_images/171c743a.png)

## Ejemplos

![](.05-etiquetado_images/627bd23d.png)
Las etiquetas deben representar dimensiones relevantes a nivel organizacional .

## AWS Config Y etiquetado

AWS config proporciona reglas administradas de AWS, que son reglas personalizables y predefinidas que AWS config utiliza
para evaluar si sus recursos de AWS se ajustan a las practicas recomendadas.

![](.05-etiquetado_images/4433358e.png)

## Etiquetado en AWS CLI

![](.05-etiquetado_images/f71941b2.png)

## Casos de uso comunes

![](.05-etiquetado_images/65b0d887.png)

## Aplicacion del etiquetado IAM

También se puede implementar la escritura de politicas de IAM que obliguen a usar ciertas etiquetas especificas. Por
Ejemplo al crear un recurso , se podria usar una politica de IAM que obligara a cumplir con el uso de las etiquetas
department y cost center a fin de lograr una generacion de informes mas precisos para la asignacion de costos.

![](.05-etiquetado_images/c3b486d2.png)

## Practicas recomendadas de etiquetado

![](.05-etiquetado_images/759fa740.png)

## Resumen

![](.05-etiquetado_images/7a46ee56.png)