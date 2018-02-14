---
title: "Numerische Ausdrücke in .NET Framework"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SIMD
- System.Numerics.Vectors
- vectors
- scientific computing
- Complex
- numerics
- BigInteger
ms.assetid: dfebc18e-acde-4510-9fa7-9a0f4aa3bd11
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: bd55b127f73fe1cefce9724f3a74400b5fe7488f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="numerics-in-the-net-framework"></a>Numerische Ausdrücke in .NET Framework
.NET Framework unterstützt die standardmäßigen numerischen Ganzzahlen und Gleitkomma-Primitive sowie <xref:System.Numerics.BigInteger>, ein ganzzahliger Typ ohne theoretische obere oder untere Grenze, <xref:System.Numerics.Complex>, einen komplexe Zahlen darstellenden Typ, und eine Reihe von SIMD-fähigen Vektortypen im <xref:System.Numerics>-Namespace.  
  
 Darüber hinaus wurde „System.Numerics.Vectors“, die Bibliothek SIMD-fähiger Vektortypen, als NuGet-Paket veröffentlicht.  
  
## <a name="integral-types"></a>Ganzzahlige Typen  
 Das .NET Framework unterstützt Ganzzahlen mit und ohne Vorzeichen mit Längen von einem bis zu acht Byte. In der folgenden Tabelle werden die ganzzahligen Typen und deren Größen aufgelistet, es wird angegeben oder sie Vorzeichen aufweisen, und der Bereich wird dokumentiert. Alle Ganzzahlen sind Werttypen.  
  
|Typ|Mit/ohne Vorzeichen|Größe (Byte)|Minimalwert|Maximalwert|  
|----------|----------------------|--------------------|-------------------|-------------------|  
|<xref:System.Byte?displayProperty=nameWithType>|Ohne Vorzeichen|1|0|255|  
|<xref:System.Int16?displayProperty=nameWithType>|Signiert|2|-32,768|32,767|  
|<xref:System.Int32?displayProperty=nameWithType>|Signiert|4|-2,147,483,648|2,147,483,647|  
|<xref:System.Int64?displayProperty=nameWithType>|Signiert|8|-9,223,372,036,854,775,808|9,223,372,036,854,775,807|  
|<xref:System.SByte?displayProperty=nameWithType>|Signiert|1|-128|127|  
|<xref:System.UInt16?displayProperty=nameWithType>|Ohne Vorzeichen|2|0|65,535|  
|<xref:System.UInt32?displayProperty=nameWithType>|Ohne Vorzeichen|4|0|4,294,967,295|  
|<xref:System.UInt64?displayProperty=nameWithType>|Ohne Vorzeichen|8|0|18,446,744,073,709,551,615|  
  
 Jeder ganzzahlige Typ unterstützt einen Standardsatz an Operatoren (arithmetisch, Vergleich, Gleichheit, explizite Konvertierung und implizite Konvertierung). Jede Ganzzahl weist darüber hinaus auch Methoden für die Durchführung von Gleichheitsvergleichen und relativen Vergleichen auf, um die Zeichenfolgendarstellung einer Zahl in diese Ganzzahl und eine Ganzzahl in die entsprechende Zeichenfolgendarstellung konvertieren zu können. Einige zusätzliche mathematische Operationen über diejenigen hinaus, die von den Standardoperatoren verarbeitet werden, wie Runden oder Erkennen des kleineren oder größeren Werts zweier Ganzzahlen stehen über die <xref:System.Math>-Klasse bereit. Sie können auch mit den einzelnen Bit in einem ganzzahligen Wert arbeiten, indem Sie die <xref:System.BitConverter>-Klasse verwenden.  
  
 Beachten Sie das ganzzahlige Typen ohne Vorzeichen nicht CLS-kompatibel sind. Weitere Informationen finden Sie unter [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../../docs/standard/language-independence-and-language-independent-components.md).  
  
## <a name="floating-point-types"></a>Gleitkommatypen  
 Das .NET Framework enthält drei primitive Gleitkommatypen, die in der folgenden Tabelle aufgeführt sind.  
  
|Typ|Größe (in Bytes)|Minimum|Maximum|  
|----------|-----------------------|-------------|-------------|  
|<xref:System.Double?displayProperty=nameWithType>|8|-1.79769313486232e308|1.79769313486232e308|  
|<xref:System.Single?displayProperty=nameWithType>|4|-3.402823e38|3.402823e38|  
|<xref:System.Decimal?displayProperty=nameWithType>|16|-79,228,162,514,264,337,593,543,950,335|79,228,162,514,264,337,593,543,950,335|  
  
 Jeder Gleitkommatyp unterstützt einen Standardsatz an Operatoren (arithmetisch, Vergleich, Gleichheit, explizite Konvertierung und implizite Konvertierung). Jeder Typ weist darüber hinaus auch Methoden für die Durchführung von Gleichheitsvergleichen und relativen Vergleichen auf, um die Zeichenfolgendarstellung einer Zahl in eine Gleitkommazahl und eine Gleitkommazahl in die entsprechende Zeichenfolgendarstellung konvertieren zu können. Einige weitere mathematische, algebraische und trigonometrische Operationen werden von der <xref:System.Math>-Klasse bereitgestellt. Sie können auch mit den einzelnen Bit in <xref:System.Double>- und <xref:System.Single>-Werten arbeiten, indem Sie die <xref:System.BitConverter>-Klasse verwenden. Die <xref:System.Decimal?displayProperty=nameWithType>-Struktur verfügt über eigene Methoden, <xref:System.Decimal.GetBits%2A?displayProperty=nameWithType> und <xref:System.Decimal.%23ctor%28System.Int32%5B%5D%29?displayProperty=nameWithType>, um mit den einzelnen Bit eines Dezimalwerts zu arbeiten, und sie verfügt über einen eigenen Satz an Methoden für die Durchführung einiger zusätzlicher mathematischer Operationen.  
  
 Die Typen <xref:System.Double> und <xref:System.Single> sind dazu gedacht, für Werte verwendet zu werden, die von Natur aus unpräzise sind (wie der Abstand zwischen zwei Sternen im Sonnensystem), und für Anwendungen, in denen kein hoher Genauigkeitsgrad mit geringen Rundungsfehlern nicht erforderlich ist. Sie sollten den <xref:System.Decimal?displayProperty=nameWithType>-Typ in Fällen verwenden, in denen eine höhere Genauigkeit erforderlich ist und Rundungsfehler unerwünscht sind.  
  
## <a name="biginteger"></a>BigInteger  
 <xref:System.Numerics.BigInteger?displayProperty=nameWithType> ist ein unveränderlicher Typ, der eine beliebig große ganze Zahl darstellt, dessen Wert theoretisch keine oberen und unteren Grenzen hat. Die Methoden des <xref:System.Numerics.BigInteger>-Typs ähneln im Wesentlichen denen der anderen ganzzahligen Typen.  
  
## <a name="complex"></a>Komplex  
 Der Typ <xref:System.Numerics.Complex> steht für eine komplexe Zahl, d. h., für eine Zahl mit einem reellen und einem imaginären Teil. Er unterstützt einen Standardsatz an Operatoren (arithmetisch, Vergleich, Gleichheit, explizite Konvertierung und implizite Konvertierung) sowie mathematische, algebraische und trigonometrische Methoden.  
  
## <a name="simd-enabled-vector-types"></a>SIMD-fähige Vektortypen  
 Der <xref:System.Numerics>-Namespace umfasst einen Satz an SIMD-fähigen Vektortypen für .NET Framework. SIMD-Operationen (Single Instruction Multiple Data) ermöglichen es, einige Operationen auf der Hardwareebene zu parallelisieren, was in mathematischen, wissenschaftlichen und grafischen Apps, die Berechnungen über Vektoren ausführen, zu einer enormen Leistungsverbesserung führt.  
  
 Die SIMD-fähigen Vektortypen in .NET Framework umfassen Folgendes:.  Darüber hinaus enthält „System.Numerics.Vectors“ einen Plane- und einen Quaternion-Typ.  
  
-   <xref:System.Numerics.Vector2>-, <xref:System.Numerics.Vector3>- und <xref:System.Numerics.Vector4>-Typen, die zwei-, drei- und vierdimensionale Vektoren vom Typ <xref:System.Single> sind.  
  
-   Zwei Matrixtypen: <xref:System.Numerics.Matrix3x2>, das eine 3x2-Matrix darstellt, und <xref:System.Numerics.Matrix4x4>, das eine 4x4-Matrix darstellt.  
  
-   Die <xref:System.Numerics.Plane>- und <xref:System.Numerics.Quaternion>-Typen.  
  
 Die SIMD-fähigen Vektortypen werden in IL implementiert, wodurch es möglich ist, sie auch auf nicht SIMD-fähiger Hardware und in Verbindung mit JIT-Compilern zu verwenden. Um SIMD-Anweisungen nutzen zu können, müssen die 64-Bit-Apps mit dem neuen 64-Bit-JIT-Compiler für verwalteten Code kompiliert werden, der in .NET Framework 4.6 enthalten ist. Er fügt die SIMD-Unterstützung hinzu, wenn x64-Prozessoren das Ziel sind.  
  
 SIMD kann auch als [NuGet-Paket](http://www.nuget.org/packages/System.Numerics.Vectors) heruntergeladen werden.  Das NuGET-Paket umfasst auch eine generische <xref:System.Numerics.Vector%601>-Struktur, mit der Sie einen Vektor eines beliebigen primitiven numerischen Typs erstellen können. (Zu den primitiven numerischen Typen gehören alle numerischen Typen im <xref:System>-Namespace außer <xref:System.Decimal>). Darüber hinaus stellt die <xref:System.Numerics.Vector%601>-Struktur eine Bibliothek von Hilfsmethoden bereit, die Sie bei der Arbeit mit Vektoren aufrufen können.  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlagen der Anwendung](../../docs/standard/application-essentials.md)
