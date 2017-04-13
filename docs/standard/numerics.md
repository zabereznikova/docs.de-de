---
title: "Numerische Ausdr&#252;cke in .NET&#160;Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "SIMD"
  - "System.Numerics.Vectors"
  - "Vektoren"
  - "Wissenschaftliche Berechnungen"
  - "Komplex"
  - "Numerische Ausdrücke"
  - "BigInteger"
ms.assetid: dfebc18e-acde-4510-9fa7-9a0f4aa3bd11
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Numerische Ausdr&#252;cke in .NET&#160;Framework
.NET Framework unterstützt die standardmäßigen numerischen Ganzzahlen und Gleitkomma-primitive sowie <xref:System.Numerics.BigInteger>, einen ganzzahligen Typ ohne theoretische obere oder untere Grenze, <xref:System.Numerics.Complex>, ein Typ, der komplexe Zahlen darstellt, sowie eine Reihe von SIMD-fähigen vektortypen in der <xref:System.Numerics> Namespace.  
  
 Darüber hinaus wurde System.Numerics.Vectors, die SIMD-fähigen Bibliothek vectory Typen als NuGet-Paket veröffentlicht.  
  
## <a name="integral-types"></a>Ganzzahlige Typen  
 Das .NET Framework unterstützt Ganzzahlen mit und ohne Vorzeichen mit Längen von einem bis zu acht Byte. In der folgenden Tabelle werden die ganzzahligen Typen und deren Größen aufgelistet, es wird angegeben oder sie Vorzeichen aufweisen, und der Bereich wird dokumentiert. Alle Ganzzahlen sind Werttypen.  
  
|Typ|Mit/ohne Vorzeichen|Größe (Byte)|Minimalwert|Maximalwert|  
|----------|----------------------|--------------------|-------------------|-------------------|  
|<xref:System.Byte?displayProperty=fullName>|Ohne Vorzeichen|1|0|255|  
|<xref:System.Int16?displayProperty=fullName>|Signiert|2|-32,768|32,767|  
|<xref:System.Int32?displayProperty=fullName>|Signiert|4|-2,147,483,648|2,147,483,647|  
|<xref:System.Int64?displayProperty=fullName>|Signiert|8|-9,223,372,036,854,775,808|9,223,372,036,854,775,807|  
|<xref:System.SByte?displayProperty=fullName>|Signiert|1|-128|127|  
|<xref:System.UInt16?displayProperty=fullName>|Ohne Vorzeichen|2|0|65,535|  
|<xref:System.UInt32?displayProperty=fullName>|Ohne Vorzeichen|4|0|4,294,967,295|  
|<xref:System.UInt64?displayProperty=fullName>|Ohne Vorzeichen|8|0|18,446,744,073,709,551,615|  
  
 Jeder ganzzahlige Typ unterstützt einen Standardsatz an Operatoren (arithmetisch, Vergleich, Gleichheit, explizite Konvertierung und implizite Konvertierung). Jede Ganzzahl weist darüber hinaus auch Methoden für die Durchführung von Gleichheitsvergleichen und relativen Vergleichen auf, um die Zeichenfolgendarstellung einer Zahl in diese Ganzzahl und eine Ganzzahl in die entsprechende Zeichenfolgendarstellung konvertieren zu können. Einige zusätzlichen mathematischen Operationen über diejenigen hinaus von den Standardoperatoren verarbeitet, wie runden oder erkennen die kleineren oder größeren Werts zweier Ganzzahlen stehen über die <xref:System.Math> Klasse. Sie können auch mit der einzelne Bits in einen ganzzahligen Wert arbeiten, mit der <xref:System.BitConverter> Klasse.  
  
 Beachten Sie das ganzzahlige Typen ohne Vorzeichen nicht CLS-kompatibel sind. Weitere Informationen finden Sie unter [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../../docs/standard/language-independence-and-language-independent-components.md).  
  
## <a name="floating-point-types"></a>Gleitkommatypen  
 Das .NET Framework enthält drei primitive Gleitkommatypen, die in der folgenden Tabelle aufgeführt sind.  
  
|Typ|Größe (in Bytes)|Minimum|Maximum|  
|----------|-----------------------|-------------|-------------|  
|<xref:System.Double?displayProperty=fullName>|8|-1.79769313486232e308|1.79769313486232e308|  
|<xref:System.Single?displayProperty=fullName>|4|-3.402823e38|3.402823e38|  
|<xref:System.Decimal?displayProperty=fullName>|16|-79,228,162,514,264,337,593,543,950,335|79,228,162,514,264,337,593,543,950,335|  
  
 Jeder Gleitkommatyp unterstützt einen Standardsatz an Operatoren (arithmetisch, Vergleich, Gleichheit, explizite Konvertierung und implizite Konvertierung). Jeder Typ weist darüber hinaus auch Methoden für die Durchführung von Gleichheitsvergleichen und relativen Vergleichen auf, um die Zeichenfolgendarstellung einer Zahl in eine Gleitkommazahl und eine Gleitkommazahl in die entsprechende Zeichenfolgendarstellung konvertieren zu können. Einige zusätzlichen mathematischen, algebraischen und trigonometrischen Operationen werden von der <xref:System.Math> Klasse. Sie können auch mit den einzelnen Bit in arbeiten <xref:System.Double> und <xref:System.Single> Werte mithilfe der <xref:System.BitConverter> Klasse. Die <xref:System.Decimal?displayProperty=fullName> Struktur verfügt über eigene Methoden, <xref:System.Decimal.GetBits%2A?displayProperty=fullName> und [Decimal.Decimal (Int32\<xref:System.Decimal.%23ctor%28System.Int32%5B%5D%29?displayProperty=fullName>für das Arbeiten mit einem Dezimalwert den einzelnen Bits als auch einen eigenen Satz von Methoden für einige zusätzlichen mathematischen Operationen ausführen.  
  
 Die <xref:System.Double> und <xref:System.Single> Typen dürfen verwendet werden, für Werte, die naturgemäß unpräzise sind (z. B. der Abstand zwischen zwei Sternen im Sonnensystem) und für Anwendungen in der ein hoher Grad an Genauigkeit mit geringen Rundungsfehlern nicht erforderlich. Verwenden Sie die <xref:System.Decimal?displayProperty=fullName> Typ für Fälle, in denen eine höhere Genauigkeit erforderlich ist und Rundungsfehler unerwünscht sind  
  
## <a name="biginteger"></a>BigInteger  
 <xref:System.Numerics.BigInteger?displayProperty=fullName> ist ein unveränderlicher Typ, der eine beliebig große ganze Zahl darstellt, deren Wert theoretisch keine Ober- und Untergrenze aufweist. Die Methoden der <xref:System.Numerics.BigInteger> -Typs ähneln im Wesentlichen denen der anderen ganzzahligen Typen.  
  
## <a name="complex"></a>Komplex  
 Die <xref:System.Numerics.Complex> Typ stellt eine komplexe Zahl, d. h. eine Zahl mit einer reellen Zahl und einem imaginären Teil. Er unterstützt einen Standardsatz an Operatoren (arithmetisch, Vergleich, Gleichheit, explizite Konvertierung und implizite Konvertierung) sowie mathematische, algebraische und trigonometrische Methoden.  
  
## <a name="simd-enabled-vector-types"></a>SIMD-fähige Vektortypen  
 Die <xref:System.Numerics> Namespace enthält eine Reihe von SIMD-fähigen vektortypen für .NET Framework. SIMD-Operationen (Single Instruction Multiple Data) ermöglichen es, einige Operationen auf der Hardwareebene zu parallelisieren, was in mathematischen, wissenschaftlichen und grafischen Apps, die Berechnungen über Vektoren ausführen, zu einer enormen Leistungsverbesserung führt.  
  
 Die SIMD-fähigen Vektortypen in .NET Framework umfassen Folgendes:.  Darüber hinaus enthält „System.Numerics.Vectors“ einen Plane- und einen Quaternion-Typ.  
  
-   <xref:System.Numerics.Vector2>, <xref:System.Numerics.Vector3>, und <xref:System.Numerics.Vector4> -Typen, die 2, 3 und 4-dimensional Vektoren vom Typ sind <xref:System.Single>.  
  
-   Zwei Matrixtypen, <xref:System.Numerics.Matrix3x2>, die stellt eine 3 x 2-Matrix; und <xref:System.Numerics.Matrix4x4>, die eine 4 x 4-Matrix darstellt.  
  
-   Die <xref:System.Numerics.Plane> und <xref:System.Numerics.Quaternion> Typen.  
  
 Die SIMD-fähigen Vektortypen werden in IL implementiert, wodurch es möglich ist, sie auch auf nicht SIMD-fähiger Hardware und in Verbindung mit JIT-Compilern zu verwenden. Um SIMD-Anweisungen nutzen zu können, müssen die 64-Bit-Apps mit dem neuen 64-Bit-JIT-Compiler für verwalteten Code kompiliert werden, der in .NET Framework 4.6 enthalten ist. Er fügt die SIMD-Unterstützung hinzu, wenn x64-Prozessoren das Ziel sind.  
  
 SIMD Download kann auch als eine [NuGet-Paket](http://www.nuget.org/packages/System.Numerics.Vectors).  Das NuGet-Paket enthält auch eine generische <xref:System.Numerics.Vector%601> -Struktur, die Sie einen Vektor, der alle primitiven numerischen Typen erstellen kann. (Die primitiven numerischen Typen umfassen alle numerische Typen in der <xref:System> Namespace, mit Ausnahme von <xref:System.Decimal>.) Darüber hinaus die <xref:System.Numerics.Vector%601> Struktur enthält eine Bibliothek mit Hilfsmethoden, die Sie bei der Arbeit mit Vektoren aufrufen können.  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlagen der Anwendung](../../docs/standard/application-essentials.md)