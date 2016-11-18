---
title: "Numerische Ausdrücke in .NET Core"
description: "Numerische Ausdrücke in .NET Core"
keywords: .NET, .NET Core
author: rpetrusha
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 6b8696be-55f5-4b66-98f3-69ff827c2c49
translationtype: Human Translation
ms.sourcegitcommit: d5c7a18af16b4f3416e84b6cf86f0f78f28948da
ms.openlocfilehash: 2930bf6879df3cd16cbd0221ae6dfcba9b41de2e

---

# <a name="numerics-in-net-core"></a>Numerische Ausdrücke in .NET Core

.NET Core unterstützt die standardmäßigen numerischen integralen und Gleitkommaprimitiven sowie [System.Numerics.BigInteger](https://docs.microsoft.com/dotnet/core/api/System.Numerics.BigInteger), einen integralen Typ ohne theoretische obere oder untere Grenze, [System.Numerics.Complex](https://docs.microsoft.com/dotnet/core/api/System.Numerics.Complex), einen komplexe Zahlen darstellenden Typ, und eine Reihe von [SIMD](https://en.wikipedia.org/wiki/SIMD)-fähigen Vektortypen (Single Instruction Multiple Data) im [System.Numerics](https://docs.microsoft.com/dotnet/core/api/System.Numerics)-Namespace. 

## <a name="integral-types"></a>Ganzzahlige Typen

.NET Core unterstützt Ganzzahlen mit und ohne Vorzeichen mit Längen von einem bis zu acht Byte. In der folgenden Tabelle werden die ganzzahligen Typen und deren Größen aufgelistet, es wird angegeben oder sie Vorzeichen aufweisen, und der Bereich wird dokumentiert. Alle Ganzzahlen sind Werttypen. 

Typ | Mit/ohne Vorzeichen | Größe (Byte) | Minimalwert | Maximalwert
---- | --------------- | ------------ | ------------- | -------------
[System.Byte](https://docs.microsoft.com/dotnet/core/api/System.Byte) | Ohne Vorzeichen | 1 | 0 | 255
[System.Int16](https://docs.microsoft.com/dotnet/core/api/System.Int16) | Signiert | 2 | -32,768 | 32,767
[System.Int32](https://docs.microsoft.com/dotnet/core/api/System.Int32) | Signiert | 4 | -2,147,483,648 | 2,147,483,647
[System.Int64](https://docs.microsoft.com/dotnet/core/api/System.Int64) | Signiert | 8 | -9,223,372,036,854,775,808 | 9,223,372,036,854,775,807
[System.SByte](https://docs.microsoft.com/dotnet/core/api/System.SByte) | Signiert | 1 | -128 | 127
[System.UInt16](https://docs.microsoft.com/dotnet/core/api/System.UInt16) | Ohne Vorzeichen | 2 | 0 | 65,535
[System.UInt32](https://docs.microsoft.com/dotnet/core/api/System.UInt32) | Ohne Vorzeichen | 4 | 0 | 4,294,967,295
[System.UInt64](https://docs.microsoft.com/dotnet/core/api/System.UInt64) | Ohne Vorzeichen | 8 | 0 | 18,446,744,073,709,551,615

Jeder ganzzahlige Typ unterstützt einen Standardsatz an Operatoren (arithmetisch, Vergleich, Gleichheit, explizite Konvertierung und implizite Konvertierung). Jede Ganzzahl weist darüber hinaus auch Methoden für die Durchführung von Gleichheitsvergleichen und relativen Vergleichen auf, um die Zeichenfolgendarstellung einer Zahl in diese Ganzzahl und eine Ganzzahl in die entsprechende Zeichenfolgendarstellung konvertieren zu können. Einige zusätzliche mathematische Operationen über diejenigen hinaus, die von den Standardoperatoren verarbeitet werden, wie z.B. das Runden oder Erkennen des kleineren oder größeren Werts zweier Ganzzahlen, stehen über die [System.Math](https://docs.microsoft.com/dotnet/core/api/System.Math)-Klasse bereit. Sie können auch mit den einzelnen Bits in einem ganzzahligen Wert arbeiten, indem Sie die [System.BitConverter](https://docs.microsoft.com/dotnet/core/api/System.BitConverter)-Klasse verwenden. 
     
Beachten Sie das ganzzahlige Typen ohne Vorzeichen nicht CLS-kompatibel sind. Weitere Informationen hierzu finden Sie unter [Allgemeines .NET-Typsystem und Common Language Specification](common-type-system.md).

## <a name="floatingpoint-types"></a>Gleitkommatypen

.NET Core enthält drei primitive Gleitkommatypen, die in der folgenden Tabelle aufgeführt sind. 

Typ | Größe (Byte) | Minimalwert | Maximalwert
---- | ------------ | ------------- | -------------
[System.Double](https://docs.microsoft.com/dotnet/core/api/System.Double) | 8 | -1.79769313486232e308 | 1.79769313486232e308
[System.Single](https://docs.microsoft.com/dotnet/core/api/System.Single) | 4 | -3.402823e38 | 3.402823e38
[System.Decimal](https://docs.microsoft.com/dotnet/core/api/System.Decimal) | 16 | -79,228,162,514,264,337,593,543,950,335 | 79,228,162,514,264,337,593,543,950,335
   
Jeder Gleitkommatyp unterstützt einen Standardsatz an Operatoren (arithmetisch, Vergleich, Gleichheit, explizite Konvertierung und implizite Konvertierung). Jeder Typ weist darüber hinaus auch Methoden für die Durchführung von Gleichheitsvergleichen und relativen Vergleichen auf, um die Zeichenfolgendarstellung einer Zahl in eine Gleitkommazahl und eine Gleitkommazahl in die entsprechende Zeichenfolgendarstellung konvertieren zu können. Einige weitere mathematische, algebraische und trigonometrische Operationen werden von der `Math`-Klasse bereitgestellt. Sie können auch mit den einzelnen Bit in `Double`- und `Single`-Werten arbeiten, indem Sie die `BitConverter`-Klasse verwenden. Die `Decimal`-Struktur verfügt über eigene Methoden, `Decimal.GetBits` und `Decimal.Decimal(Int32())`, um mit den einzelnen Bit eines Dezimalwerts zu arbeiten, und sie verfügt über einen eigenen Satz an Methoden für die Durchführung einiger zusätzlicher mathematischer Operationen. 

Die Typen `Double` und `Single` sind dazu gedacht, für Werte verwendet zu werden, die von Natur aus unpräzise sind (wie der Abstand zwischen zwei Sternen im Sonnensystem), und für Anwendungen, in denen kein hoher Genauigkeitsgrad mit geringen Rundungsfehlern nicht erforderlich ist. Sie sollten den `Decimal`-Typ in Fällen verwenden, in denen eine höhere Genauigkeit erforderlich ist und Rundungsfehler unerwünscht sind.

## <a name="biginteger"></a>BigInteger

[System.Numerics.BigInteger](https://docs.microsoft.com/dotnet/core/api/System.Numerics.BigInteger) ist ein unveränderlicher Typ, der eine beliebig große ganze Zahl darstellt, deren Wert theoretisch keine Ober- und Untergrenze aufweist. Die Methoden des `BigInteger`-Typs ähneln im Wesentlichen denen der anderen ganzzahligen Typen.  

## <a name="complex"></a>Komplex

Der Typ [System.Numerics.Complex](https://docs.microsoft.com/dotnet/core/api/System.Numerics.Complex) steht für eine komplexe Zahl, d.h. für eine Zahl mit einem reellen und einem imaginären Teil. Er unterstützt einen Standardsatz an Operatoren (arithmetisch, Vergleich, Gleichheit, explizite Konvertierung und implizite Konvertierung) sowie mathematische, algebraische und trigonometrische Methoden. 

## <a name="simdenabled-vector-types"></a>SIMD-fähige Vektortypen

Der `System.Numerics`-Namespace umfasst einen Satz von SIMD-fähigen Vektortypen für .NET Core. Anhand von SIMD-Operationen können einige Operationen auf der Hardwareebene parallelisiert werden, was in mathematischen, wissenschaftlichen und grafischen Apps, die Berechnungen über Vektoren ausführen, zu einer enormen Leistungsverbesserung führt. 

Zu den SIMD-fähigen Vektortypen in .NET Core gehören Folgende: 

* Die Typen [System.Numerics.Vector2](https://docs.microsoft.com/dotnet/core/api/System.Numerics.Vector2), [System.Numerics.Vector3](https://docs.microsoft.com/dotnet/core/api/System.Numerics.Vector3) und [System.Numerics.Vector4](https://docs.microsoft.com/dotnet/core/api/System.Numerics.Vector4), die zwei-, drei- und vierdimensionale Vektoren vom Typ `Single` sind.

* Die [Vector&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Numerics.Vector-1)-Struktur, durch die Sie einen Vektor jedes primitiven numerischen Typs erstellen können. Zu den primitiven numerischen Typen gehören alle numerischen Typen im System-Namespace außer Dezimalwerte.

* Zwei Matrixtypen, [System.Numerics.Matrix3x2](https://docs.microsoft.com/dotnet/core/api/System.Numerics.Matrix3x2) zur Darstellung einer 3×2-Matrix und [System.Numerics.Matrix4x4](https://docs.microsoft.com/dotnet/core/api/System.Numerics.Matrix4x4) zur Darstellung einer 4×4-Matrix. 

* Der Typ [System.Numerics.Plane](https://docs.microsoft.com/dotnet/core/api/System.Numerics.Plane), der eine dreidimensionale Ebene darstellt, und der Typ [System.Numerics.Quaternion](https://docs.microsoft.com/dotnet/core/api/System.Numerics.Quaternion), der einen Vektor zum Codieren dreidimensionaler physischer Drehungen darstellt.



<!--HONumber=Nov16_HO3-->


