---
title: Numerische Ausdrücke in .NET
ms.date: 10/18/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- SIMD
- System.Numerics.Vectors
- vectors
- scientific computing
- Complex
- numerics
- BigInteger
ms.assetid: dfebc18e-acde-4510-9fa7-9a0f4aa3bd11
ms.openlocfilehash: 3b95a322377e82249a0375af589df74c658fcbf4
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507415"
---
# <a name="numerics-in-net"></a>Numerische Ausdrücke in .NET

.NET stellt zahlreiche numerische Ganzzahl- und Gleitkomma-Grundtypen sowie <xref:System.Numerics.BigInteger?displayProperty=nameWithType> (Ganzzahltyp ohne theoretische Ober- oder Untergrenze), <xref:System.Numerics.Complex?displayProperty=nameWithType> (komplexe Zahlen darstellender Typ) und eine Reihe von SIMD-fähigen Typen im <xref:System.Numerics>-Namespace zur Verfügung.
  
## <a name="integer-types"></a>Ganzzahltypen

.NET unterstützt 8-, 16-, 32- und 64-Bit-Ganzzahltypen mit und ohne Vorzeichen, die in der folgenden Tabelle aufgeführt sind:
  
|Typ|Mit/ohne Vorzeichen|Größe (in Bytes)|Minimalwert|Maximalwert|  
|----------|----------------------|--------------------|-------------------|-------------------|  
|<xref:System.Byte?displayProperty=nameWithType>|Ohne Vorzeichen|1|0|255|  
|<xref:System.Int16?displayProperty=nameWithType>|Signiert|2|-32,768|32,767|  
|<xref:System.Int32?displayProperty=nameWithType>|Signiert|4|-2,147,483,648|2,147,483,647|  
|<xref:System.Int64?displayProperty=nameWithType>|Signiert|8|-9,223,372,036,854,775,808|9,223,372,036,854,775,807|  
|<xref:System.SByte?displayProperty=nameWithType>|Signiert|1|-128|127|  
|<xref:System.UInt16?displayProperty=nameWithType>|Ohne Vorzeichen|2|0|65,535|  
|<xref:System.UInt32?displayProperty=nameWithType>|Ohne Vorzeichen|4|0|4,294,967,295|  
|<xref:System.UInt64?displayProperty=nameWithType>|Ohne Vorzeichen|8|0|18,446,744,073,709,551,615|  
  
Jeder Ganzzahltyp unterstützt eine Reihe von arithmetischen Standardoperatoren. Die Klasse <xref:System.Math?displayProperty=nameWithType> stellt Methoden für mehrere mathematische Funktionen bereit.

Sie können auch mit den einzelnen Bit in einem ganzzahligen Wert arbeiten, indem Sie die <xref:System.BitConverter?displayProperty=nameWithType>-Klasse verwenden.  

> [!NOTE]  
> Die Ganzzahltypen ohne Vorzeichen sind nicht CLS-kompatibel. Weitere Informationen finden Sie unter [Sprachenunabhängigkeit und sprachunabhängige Komponenten](language-independence-and-language-independent-components.md).

## <a name="biginteger"></a>BigInteger

Die <xref:System.Numerics.BigInteger?displayProperty=nameWithType>-Struktur ist ein unveränderlicher Typ, der eine beliebig große ganze Zahl darstellt, dessen Wert theoretisch keine Ober- und Untergrenze hat. Die Methoden des <xref:System.Numerics.BigInteger>-Typs ähneln im Wesentlichen denen der anderen ganzzahligen Typen.
  
## <a name="floating-point-types"></a>Gleitkommatypen

.NET enthält drei grundlegende Gleitkommatypen, die in der folgenden Tabelle aufgeführt sind:
  
|Typ|Größe (in Bytes)|Ungefährer Bereich|Genauigkeit|  
|----------|--------|---------------------|--------------------|  
|<xref:System.Single?displayProperty=nameWithType>|4|±1.5 × 10<sup>−45</sup> zu ±3.4 × 10<sup>38</sup>|~6–9 Stellen|  
|<xref:System.Double?displayProperty=nameWithType>|8|±5,0 × 10<sup>−324</sup> bis ±1,7 × 10<sup>308</sup>|~15–17 Stellen|  
|<xref:System.Decimal?displayProperty=nameWithType>|16|±1.0 × 10<sup>-28</sup> to ±7.9228 × 10<sup>28</sup>|28-29 Stellen|  
  
Die beiden Typen <xref:System.Single> und <xref:System.Double> unterstützen spezielle Werte, die „nicht numerisch“ und „unendlich“ darstellen. Der Typ <xref:System.Double> liefert beispielsweise die folgenden Werte: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> und <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>. Mit den Methoden <xref:System.Double.IsNaN%2A?displayProperty=nameWithType>, <xref:System.Double.IsInfinity%2A?displayProperty=nameWithType>, <xref:System.Double.IsPositiveInfinity%2A?displayProperty=nameWithType> und <xref:System.Double.IsNegativeInfinity%2A?displayProperty=nameWithType> können Sie Tests für diese speziellen Werte ausführen.

Jeder Gleitkommatyp unterstützt eine Reihe von arithmetischen Standardoperatoren. Die Klasse <xref:System.Math?displayProperty=nameWithType> stellt Methoden für mehrere mathematische Funktionen bereit. .NET Core 2.0 und höher enthält die Klasse <xref:System.MathF?displayProperty=nameWithType>, die Methoden bereitstellt, die Argumente vom Typ <xref:System.Single> akzeptieren.

Sie können auch mit den einzelnen Bit in <xref:System.Double>- und <xref:System.Single>-Werten arbeiten, indem Sie die <xref:System.BitConverter?displayProperty=nameWithType>-Klasse verwenden. Die <xref:System.Decimal?displayProperty=nameWithType>-Struktur verfügt über eigene Methoden, <xref:System.Decimal.GetBits%2A?displayProperty=nameWithType> und <xref:System.Decimal.%23ctor%28System.Int32%5B%5D%29>, um mit den einzelnen Bit eines Dezimalwerts zu arbeiten, und sie verfügt über einen eigenen Satz an Methoden für die Durchführung einiger zusätzlicher mathematischer Operationen.
  
Die Typen <xref:System.Double> und <xref:System.Single> sind dazu gedacht, für Werte verwendet zu werden, die per se unpräzise sind (wie der Abstand zwischen zwei Sternen), und für Anwendungen, in denen kein hoher Genauigkeitsgrad erforderlich ist und geringe Rundungsfehler auftreten dürfen. Verwenden Sie den <xref:System.Decimal?displayProperty=nameWithType>-Typ in Fällen, in denen eine höhere Genauigkeit erforderlich ist und Rundungsfehler minimiert werden sollen.

> [!NOTE]
> Der Typ <xref:System.Decimal> ersetzt nicht die Notwendigkeit der Rundung. Stattdessen reduziert er Fehler, die beim Runden auftreten.
  
## <a name="complex"></a>Komplex

Die <xref:System.Numerics.Complex?displayProperty=nameWithType>-Struktur steht für eine komplexe Zahl, d.h., für eine Zahl mit einem reellen und einem imaginären Teil. Sie unterstützt einen Standardsatz an Operatoren (arithmetisch, Vergleich, Gleichheit, explizite Konvertierung und implizite Konvertierung) sowie mathematische, algebraische und trigonometrische Methoden.  
  
## <a name="simd-enabled-types"></a>SIMD-fähige Typen

Der <xref:System.Numerics>-Namespace umfasst einen Satz von SIMD-fähigen .NET-Typen. SIMD-Vorgänge (Single Instruction Multiple Data) lassen sich auf Hardwareebene parallelisieren. Das erhöht den Durchsatz der vektorisierten Berechnungen, die in mathematischen, wissenschaftlichen und grafischen Apps üblich sind.
  
Die SIMD-fähigen .NET-Typen umfassen Folgendes:

- Die Typen <xref:System.Numerics.Vector2>, <xref:System.Numerics.Vector3> und <xref:System.Numerics.Vector4>, die Vektoren mit 2, 3 und 4 <xref:System.Single>-Werten darstellen.

- Die zwei Matrixtypen <xref:System.Numerics.Matrix3x2> und <xref:System.Numerics.Matrix4x4>. Der erste Typ stellt eine 3x2-Matrix und der zweite eine 4x4-Matrix dar.

- Den <xref:System.Numerics.Plane>-Typ, der eine Ebene im dreidimensionalen Raum darstellt.

- Den <xref:System.Numerics.Quaternion>-Typ, der einen Vektor darstellt, der zum Codieren von dreidimensionalen physischen Drehungen verwendet wird.

- Den <xref:System.Numerics.Vector%601>-Typ, der einen Vektor eines bestimmten numerischen Typs darstellt und mehrere Operatoren bereitstellt, die von der SIMD-Unterstützung profitieren. Die Anzahl von <xref:System.Numerics.Vector%601>-Instanzen ist fest, aber ihr Wert <xref:System.Numerics.Vector%601.Count%2A?displayProperty=nameWithType> hängt von der CPU des Computers ab, auf dem der Code ausgeführt wird.
  > [!NOTE]
  > Der <xref:System.Numerics.Vector%601>-Typ ist nicht in .NET Framework enthalten. Sie müssen das NuGet-Paket [System.Numerics.Vectors](https://www.nuget.org/packages/System.Numerics.Vectors) installieren, um Zugriff auf diesen Typ zu erhalten.
  
Die SIMD-fähigen Typen sind so implementiert, dass sie mit nicht-SIMD-fähiger Hardware oder JIT-Compilern verwendet werden können. Um die Vorteile von SIMD-Anweisungen zu nutzen, müssen Ihre 64-Bit-Apps von der Runtime ausgeführt werden, die den RyuJIT-Compiler verwendet, der in .NET Core und in .NET Framework 4.6 und höher enthalten ist. Sie fügt SIMD-Unterstützung hinzu, wenn 64-Bit-Prozessoren verwendet werden.

Weitere Informationen finden Sie unter [Verwenden von mit SIMD beschleunigter numerischer Typen](simd.md).

## <a name="see-also"></a>Siehe auch

- [Standardmäßige Zahlenformatzeichenfolgen](base-types/standard-numeric-format-strings.md)
