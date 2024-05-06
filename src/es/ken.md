---
title: Kensetsu KEN | Documentos SORA
head:
   - - meta
     - name: descripción
       content: Obtenga más información sobre KENSETSU, el equivalente MakerDAO de SORA, que incluye la quema de tokens XOR, las recompensas de tokens KEN y el papel de Kensetsu en el espacio DeFi en Polkadot.
   - - meta
     - name: palabras clave
       content: quema de tokens, SORA, Maker DAO, moneda estable
---

# Kensetsu KEN

::: información
Este token fue propuesto originalmente en [SORA RFP 60](https://github.com/sora-xor/rfps/issues/60) por Satoshi Shibarimoto.
:::

## TL;DR

- Todos los tokens KEN iniciales se distribuirán a cuentas que quemen al menos 1 millón de XOR entre los bloques 14.464.000 y 14.939.200.
- Quemar menos de 1 millón de XOR no producirá tokens KEN
- El 1% de todas las monedas estables de Kensetsu acuñadas se utilizará para recomprar y quemar KEN en Polkaswap.
- El 80% de los KEN quemados diariamente se recordarán y se entregarán a Demeter Farm para obtener recompensas agrícolas en el grupo XOR-KUSD, para incentivar la liquidez.

## Introducción a Kensetsu

Con KENSETSU, los poseedores de tokens XOR podrán votar para crear monedas estables vinculadas a cualquier valor disponible a través de oráculos en la red SORA, como las populares monedas fiduciarias, ORO, PLATA y otras. Al igual que con Maker DAO, los usuarios pueden acuñar monedas estables encerrando garantías en bóvedas.

En KENSETSU, habrá dos tipos de bóveda:

1. Bóvedas donde los usuarios guardan garantías y pueden recuperarlas pagando las monedas estables acuñadas.
2. Bóvedas donde los usuarios guardan garantías, pero para recuperarlas tendrán que pagar las monedas estables acuñadas + una tarifa de estabilidad.

Las bóvedas de tipo 1 no se pueden liquidar, pero habrá una tarifa de estabilidad como impuesto que se deduce de la garantía a lo largo del tiempo, por lo que los usuarios nunca recuperarán la totalidad de su garantía. Las bóvedas de tipo 2 pueden liquidarse si el valor de la garantía subyacente baja demasiado.
Se espera que los activos de garantía iniciales sean XOR, TBCD, VAL, PSWAP, ETH y DAI.

La capacidad de acuñar monedas estables a partir de garantías es muy útil. Aún así, debido a que existe una tarifa de estabilidad en las bóvedas, también es necesario que las monedas estables sean líquidas y generen demanda. Ahí es donde entra KEN.

## KENONOMÍA

KEN es un token de recompensa agrícola destinado a incentivar la liquidez de las monedas estables de KENSETSU. Por cada moneda estable acuñada a partir de garantía depositada, se acuñará un 1% adicional de la moneda estable y se utilizará para recomprar y quemar tokens KEN.
El 80% de los tokens KEN quemados se recordarán y distribuirán a la granja Demeter para obtener recompensas en el grupo XOR-KUSD en Polkaswap.
Para aumentar las apuestas, para obtener una asignación del suministro inicial de KEN, literalmente tendrá que quemar dinero.
KEN será estrictamente deflacionario una vez lanzado, lo que significa que el suministro solo disminuirá; además, KEN solo se asignará a cuentas en la red SORA que quemen (usando el extrínseco `assets.burn`) al menos 1 millón de XOR, a una tasa de 1 KEN por cada millón de XOR quemado. Solo puedes obtener los tokens KEN iniciales quemando XOR.

## Cómo grabar XOR

Se puede grabar XOR por diversión y ganancias utilizando la ingeniosa interfaz de dotapps. Simplemente haga clic en [este enlace](https://polkadot.js.org/apps/#/extrinsics) y complete el formulario de la siguiente manera:

![](/.gitbook/assets/ken-burn-extrinsics.png)

Para llenar el formulario:

1. Seleccione el módulo de activos y grabe el `(assets.burn)` extrínseco
2. Seleccione la cuenta que tiene el XOR que desea grabar.
3. El ID del activo que se va a grabar es XOR: `0x0200000000000000000000000000000000000000000000000000000000000000`
4. Para la cantidad, necesita 18 ceros después de la cantidad de XOR que desea quemar, por lo que quemar 1 millón de XOR es: `10000000000000000000000000`.
5. Luego firme la transacción y confirme que su saldo XOR disminuyó correctamente, lo que demuestra que quemó el XOR.

Todo XOR quemado llamando al extrínseco `assets.burn` entre los bloques `14,464,000` y `14,939,200` se considerará en la cantidad quemada calculada. Para ser elegible para la caída de KEN, una cuenta debe quemar al menos 1 millón de XOR. Se entregará 1 KEN por cada millón de XOR quemado.

Por ejemplo, si se queman 999,999 XOR, se le dará 0 KEN a un
cuenta. Si se queman 1 millón de XOR, se entregará 1 KEN a un
cuenta. Y si se queman 1,6 millones de XOR, se darán 1,6 KEN
a una cuenta.

::: información
Puede rastrear el XOR quemado en la interfaz de Polkaswap [Kensetsu
pestaña](https://polkaswap.io/#/kensetsu).
La reserva de KEN mediante la quema de XOR finalizó el 20 de marzo de 2024
:::

> Este artículo fue publicado originalmente en [Medium](https://medium.com/@shibarimoto/kensetsu-ken-356077ebee78) y escrito por el miembro de la comunidad Satoshi Shibarimoto. Esta entrada conserva los principios básicos de _Kenonomics_.

## Aprende más

- [VAL Tokenomics](/val.md)
- [Solicitud de funciones en SORA](/rfp.md)