---
title: Typkonvertierung in .NET
description: Erfahren Sie mehr über die Typkonvertierung in .NET, bei der ein Wert mit einem neuen Typ erstellt wird, der dem Wert mit dem alten Typ entspricht, die Identität des ursprünglichen Typs jedoch möglicherweise nicht beibehält.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- widening conversions
- explicit conversions
- narrowing conversions
- type conversion, about type conversion
- type conversion
- converting types
- narrowing coercion
- Explicit operator
- IConvertible interface
- base types, converting
- op_Implicit method
- widening coercion
- op_Explicit method
- Convert class
- implicit conversions
- Implicit operator
- data types [.NET], converting
ms.assetid: ba36154f-064c-47d3-9f05-72f93a7ca96d
ms.openlocfilehash: 4f7e4400aa15532b04fd4e39219775af34068685
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687539"
---
# <a name="type-conversion-in-net"></a>Typkonvertierung in .NET

Jeder Wert verfügt über einen zugeordneten Typ, durch den Attribute, z. B. der dem Wert zugewiesene Speicherplatz, der zulässige Wertebereich und die verfügbar gemachten Member, festgelegt werden. Viele Werte können durch mehrere Typen ausgedrückt werden. Beispielsweise kann der Wert 4 als ganze Zahl oder als Gleitkommawert dargestellt werden. Durch Typkonvertierung wird ein Wert neuen Typs erstellt, der mit dem Wert des alten Typs äquivalent ist. Die Identität (oder der exakte Wert) des ursprünglichen Objekts bleibt dabei nicht immer erhalten.  
  
.NET unterstützt automatisch die folgenden Konvertierungen:  
  
- Die Konvertierung von einer abgeleiteten Klasse in eine Basisklasse. Dies bedeutet beispielsweise, dass eine Instanz einer beliebigen Klasse oder Struktur in eine <xref:System.Object>-Instanz konvertiert werden kann.  Diese Konvertierung erfordert keinen Umwandlungs- oder Konvertierungsoperator.  
  
- Die Konvertierung von einer Basisklasse in die ursprünglich abgeleitete Klasse. In C# erfordert diese Konvertierung einen Umwandlungsoperator. Visual Basic erfordert für diese Konvertierung den Operator `CType`, wenn für `Option Strict` „On“ gesetzt ist.  
  
- Die Konvertierung von einem Typ, der eine Schnittstelle in einem Schnittstellenobjekt implementiert, das diese Schnittstelle darstellt. Diese Konvertierung erfordert keinen Umwandlungs- oder Konvertierungsoperator.  
  
- Die Konvertierung von einem Schnittstellenobjekt zurück in den ursprünglichen Typ, der diese Schnittstelle implementiert.  In C# erfordert diese Konvertierung einen Umwandlungsoperator. Visual Basic erfordert für diese Konvertierung den Operator `CType`, wenn für `Option Strict` „On“ gesetzt ist.  
  
Zusätzlich zu diesen automatischen Konvertierungen bietet .NET verschiedene Funktionen, die die benutzerdefinierte Typkonvertierung unterstützen. Hierzu gehört Folgendes:  
  
- Der `Implicit`-Operator, der die verfügbaren Erweiterungskonvertierungen zwischen Typen definiert. Weitere Informationen finden Sie im Abschnitt [Implizite Konvertierung mit dem Implicit-Operator](#implicit-conversion-with-the-implicit-operator).  
  
- Der `Explicit`-Operator, der die verfügbaren einschränkenden Konvertierungen zwischen Typen definiert. Weitere Informationen finden Sie im Abschnitt [Explizite Konvertierung mit dem Explicit-Operator](#explicit-conversion-with-the-explicit-operator).  
  
- Die Schnittstelle <xref:System.IConvertible>, die Konvertierungen in die einzelnen .NET-Basisdatentypen definiert. Weitere Informationen finden Sie unter [Die IConvertible-Schnittstelle](#the-iconvertible-interface).  
  
- Die <xref:System.Convert>-Klasse, die einen Satz von Methoden bereitstellt, mit denen die Methoden in der <xref:System.IConvertible>-Schnittstelle implementiert werden. Weitere Informationen finden Sie unter [Die Convert-Klasse](#the-convert-class).  
  
- Die <xref:System.ComponentModel.TypeConverter>-Klasse, die eine Basisklasse ist, die für die Unterstützung der Konvertierung eines angegebenen Typs in einen beliebigen anderen Typ erweitert werden kann. Weitere Informationen finden Sie im Abschnitt [Die TypeConverter-Klasse](#the-typeconverter-class).  

## <a name="implicit-conversion-with-the-implicit-operator"></a>Implizite Konvertierung mit dem implicit-Operator

Erweiterungskonvertierungen umfassen die Erstellung eines neuen Werts aus dem Wert eines vorhandenen Typs, der einen restriktiveren Bereich oder eine eingeschränktere Memberliste als der Zieltyp aufweist. Erweiterungskonvertierungen können nicht zu Datenverlust, möglicherweise jedoch zu einem Genauigkeitsverlust führen. Da keine Daten verloren gehen können, können Compiler die Konvertierung implizit oder transparent behandeln, ohne eine explizite Konvertierungsmethode oder einen Typumwandlungsoperator verwenden zu müssen.  
  
> [!NOTE]
> Obwohl in Code, der eine implizite Konvertierung ausführt, eine Konvertierungsmethode aufgerufen oder ein Typumwandlungsoperator verwendet werden kann, ist ihre Verwendung für Compiler, die implizite Konvertierungen unterstützen, nicht erforderlich.  
  
 Beispielsweise unterstützt der <xref:System.Decimal>-Typ implizite Konvertierungen aus Werten vom Typ <xref:System.Byte>, <xref:System.Char>, <xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.SByte>, <xref:System.UInt16>, <xref:System.UInt32> und <xref:System.UInt64>. Im folgenden Beispiel werden einige dieser impliziten Konvertierungen beim Zuweisen von Werten zu einer <xref:System.Decimal>-Variablen veranschaulicht.  
  
 [!code-csharp[Conceptual.Conversion#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.conversion/cs/implicit1.cs#1)]
 [!code-vb[Conceptual.Conversion#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.conversion/vb/implicit1.vb#1)]  
  
 Wenn ein bestimmter Sprachcompiler benutzerdefinierte Operatoren unterstützt, können Sie auch implizite Konvertierungen in die eigenen benutzerdefinierten Typen definieren. Im folgenden Beispiel wird die partielle Implementierung des Byte-Datentyps mit Vorzeichen `ByteWithSign` bereitgestellt, der eine Vorzeichen-Wert-Darstellung verwendet. Sie unterstützt die implizite Konvertierung von <xref:System.Byte>-Werten und <xref:System.SByte>-Werten in `ByteWithSign`-Werte.  
  
 [!code-csharp[Conceptual.Conversion#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.conversion/cs/implicit1.cs#2)]
 [!code-vb[Conceptual.Conversion#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.conversion/vb/implicit1.vb#2)]  
  
 Clientcode kann dann eine `ByteWithSign`-Variable deklarieren und ihr <xref:System.Byte>-Werte sowie <xref:System.SByte>-Werte zuweisen, ohne eine explizite Konvertierung auszuführen oder Typumwandlungsoperatoren zu verwenden, wie im folgenden Beispiel gezeigt.  
  
 [!code-csharp[Conceptual.Conversion#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.conversion/cs/implicit1.cs#3)]
 [!code-vb[Conceptual.Conversion#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.conversion/vb/implicit1.vb#3)]  

## <a name="explicit-conversion-with-the-explicit-operator"></a>Explizite Konvertierung mit dem explicit-Operator

Einschränkende Konvertierungen umfassen die Erstellung eines neuen Werts aus dem Wert eines vorhandenen Typs, der einen größeren Bereich oder eine größere Memberliste als der Zieltyp aufweist. Da eine einschränkende Konvertierung zu Datenverlust an Daten führen kann, erfordern Compiler oft, dass die Konvertierung durch den Aufruf einer Konvertierungsmethode oder eines Typumwandlungsoperators als explizite Konvertierung erfolgt. Das bedeutet, dass die Konvertierung in Entwicklercode explizit behandelt werden muss.  
  
> [!NOTE]
> Eine Konvertierungsmethode oder ein Typumwandlungsoperator ist vor allem deswegen für einschränkende Konvertierungen erforderlich, um den Entwickler auf die Möglichkeit von Datenverlust oder einer <xref:System.OverflowException> aufmerksam zu machen, damit sie in Code behandelt werden kann. Bei einigen Compilern wird diese Anforderung jedoch weniger streng gehandhabt. Wenn beispielsweise in Visual Basic `Option Strict` deaktiviert ist (die Standardeinstellung), versucht der Visual Basic-Compiler, einschränkende Konvertierungen implizit auszuführen.  
  
 Beispielsweise weisen die Datentypen <xref:System.UInt32>, <xref:System.Int64> und <xref:System.UInt64> größere Bereiche als der <xref:System.Int32>-Datentyp auf, wie in der folgenden Tabelle gezeigt.  
  
|Typ|Vergleich mit Bereich von Int32|  
|----------|------------------------------------|  
|<xref:System.Int64>|<xref:System.Int64.MaxValue?displayProperty=nameWithType> ist größer als <xref:System.Int32.MaxValue?displayProperty=nameWithType>, und <xref:System.Int64.MinValue?displayProperty=nameWithType> ist kleiner als (hat größeren negativen Bereich als) <xref:System.Int32.MinValue?displayProperty=nameWithType>.|  
|<xref:System.UInt32>|<xref:System.UInt32.MaxValue?displayProperty=nameWithType> ist größer als <xref:System.Int32.MaxValue?displayProperty=nameWithType>.|  
|<xref:System.UInt64>|<xref:System.UInt64.MaxValue?displayProperty=nameWithType> ist größer als <xref:System.Int32.MaxValue?displayProperty=nameWithType>.|  
  
 Um solche einschränkenden Konvertierungen zu behandeln, ermöglicht .NET Typen das Definieren eines `Explicit`-Operators. Einzelne Sprachcompiler können diesen Operator dann mithilfe einer eigenen Syntax implementieren, oder ein Member der <xref:System.Convert>-Klasse kann aufgerufen werden, um die Konvertierung auszuführen. (Weitere Informationen zur <xref:System.Convert>-Klasse finden Sie unter [Die Convert-Klasse](#the-convert-class) weiter unten in diesem Thema.) Das folgende Beispiel veranschaulicht die Verwendung von Sprachfunktionen, um die explizite Konvertierung dieser potenziell außerhalb des Gültigkeitsbereichs liegenden ganzzahligen Werte in <xref:System.Int32>-Werte zu behandeln.  
  
 [!code-csharp[Conceptual.Conversion#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.conversion/cs/explicit1.cs#4)]
 [!code-vb[Conceptual.Conversion#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.conversion/vb/explicit1.vb#4)]  
  
 Explizite Konvertierungen können in verschiedenen Sprachen zu unterschiedlichen Ergebnissen führen, und diese Ergebnisse können sich von dem Wert unterscheiden, der von der entsprechenden <xref:System.Convert>-Methode zurückgegeben wird. Bei der Konvertierung des <xref:System.Double>-Werts 12.63251 in eine <xref:System.Int32>-Struktur wird <xref:System.Double> von der Visual Basic-Methode `CInt` und der .NET-Methode <xref:System.Convert.ToInt32%28System.Double%29?displayProperty=nameWithType> aufgerundet, und der Wert 13 wird zurückgegeben. Der C#-Operator `(int)` kürzt <xref:System.Double> jedoch und gibt den Wert 12 zurück. Entsprechend unterstützt der `(int)`-Operator von C# keine Konvertierung von booleschen Werten in Ganzzahlwerte, wohingegen die `CInt`-Methode von Visual Basic den Wert `true` in -1 konvertiert. Dagegen konvertiert die <xref:System.Convert.ToInt32%28System.Boolean%29?displayProperty=nameWithType>-Methode den Wert `true` in 1.  
  
 Die meisten Compiler ermöglichen die überprüfte und nicht überprüfte Ausführung expliziter Konvertierungen. Bei überprüften Konvertierungen wird eine <xref:System.OverflowException> ausgelöst, wenn der Wert des konvertierten Typs außerhalb des Bereichs des Zieltyps liegt. Wird unter denselben Umständen eine nicht überprüfte Konvertierung durchgeführt, wird möglicherweise keine Ausnahme ausgelöst. Die genauen Auswirkungen lassen sich jedoch nicht vorhersagen. Dies kann zu einem fehlerhaften Wert führen.  
  
> [!NOTE]
> In C# können überprüfte Konvertierungen mithilfe des Schlüsselworts `checked` zusammen mit einem Umwandlungsoperator oder durch Festlegen der Compileroption `/checked+` ausgeführt werden. Umgekehrt können nicht überprüfte Konvertierungen mithilfe des Schlüsselworts `unchecked` zusammen mit dem Umwandlungsoperator oder durch Festlegen der Compileroption `/checked-` ausgeführt werden. In der Standardeinstellung werden explizite Konvertierungen nicht überprüft. In Visual Basic können überprüfte Konvertierungen durch Deaktivieren des Kontrollkästchens **Überprüfungen auf Ganzzahlüberlauf entfernen** im Dialogfeld **Erweiterte Compilereinstellungen** des Projekts oder durch Festlegen der Compileroption `/removeintchecks-` ausgeführt werden. Umgekehrt können nicht überprüfte Konvertierungen durch Aktivieren des Kontrollkästchens **Überprüfungen auf Ganzzahlüberlauf entfernen** im Dialogfeld **Erweiterte Compilereinstellungen** des Projekts oder durch Festlegen der Compileroption `/removeintchecks+` ausgeführt werden. In der Standardeinstellung werden explizite Konvertierungen überprüft.  
  
 Im folgenden C#-Beispiel wird mit dem `checked`-Schlüsselwort und mit dem `unchecked`-Schlüsselwort das unterschiedliche Verhalten bei der Konvertierung eines Werts außerhalb des <xref:System.Byte>-Bereichs in eine <xref:System.Byte> veranschaulicht. Die überprüfte Konvertierung löst eine Ausnahme aus, während die nicht überprüfte Konvertierung <xref:System.Byte.MaxValue?displayProperty=nameWithType> der Variablen <xref:System.Byte> zuweist.  
  
 [!code-csharp[Conceptual.Conversion#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.conversion/cs/explicit1.cs#12)]  
  
 Wenn ein bestimmter Sprachcompiler benutzerdefinierte überladene Operatoren unterstützt, können Sie auch explizite Konvertierungen in die eigenen benutzerdefinierten Typen definieren. Im folgenden Beispiel wird die partielle Implementierung des Byte-Datentyps mit Vorzeichen `ByteWithSign` bereitgestellt, der eine Vorzeichen-Wert-Darstellung verwendet. Sie unterstützt die explizite Konvertierung von <xref:System.Int32>-Werten und <xref:System.UInt32>-Werten in `ByteWithSign`-Werte.  
  
 [!code-csharp[Conceptual.Conversion#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.conversion/cs/explicit1.cs#5)]
 [!code-vb[Conceptual.Conversion#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.conversion/vb/explicit1.vb#5)]  
  
 In Clientcode kann dann eine `ByteWithSign`-Variable deklariert werden, der <xref:System.Int32>-Werte und <xref:System.UInt32>-Werte zugewiesen werden, wenn die Zuweisungen einen Typumwandlungsoperator oder eine Konvertierungsmethode umfassen, wie im folgenden Beispiel gezeigt.  
  
 [!code-csharp[Conceptual.Conversion#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.conversion/cs/explicit1.cs#6)]
 [!code-vb[Conceptual.Conversion#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.conversion/vb/explicit1.vb#6)]  

## <a name="the-iconvertible-interface"></a>Die IConvertible-Schnittstelle

Damit die Konvertierung eines beliebigen Typs in einen Common Language Runtime-Basistyp unterstützt wird, stellt .NET die Schnittstelle <xref:System.IConvertible> bereit. Der Implementierungstyp ist erforderlich, um folgende Elemente bereitzustellen:  
  
- Eine Methode, die den <xref:System.TypeCode> des Implementierungstyps zurückgibt.  
  
- Methoden, um den Implementierungstyp in die einzelnen Common Language Runtime-Basistypen (<xref:System.Boolean>, <xref:System.Byte>, <xref:System.DateTime>, <xref:System.Decimal>, <xref:System.Double> usw.) zu konvertieren.  
  
- Eine allgemeine Konvertierungsmethode, um eine Instanz des Implementierungstyps in einen anderen angegebenen Typ zu konvertieren. Konvertierungen, die nicht unterstützt werden, sollten eine <xref:System.InvalidCastException> auslösen.  
  
 Die einzelnen Common Language Runtime-Basistypen (d. h. <xref:System.Boolean>, <xref:System.Byte>, <xref:System.Char>, <xref:System.DateTime>, <xref:System.Decimal>, <xref:System.Double>, <xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.SByte>, <xref:System.Single>, <xref:System.String>, <xref:System.UInt16>, <xref:System.UInt32> und <xref:System.UInt64>) sowie der <xref:System.DBNull>-Typ und der <xref:System.Enum>-Typ implementieren die <xref:System.IConvertible>-Schnittstelle. Dies sind jedoch explizite Schnittstellenimplementierungen. Die Konvertierungsmethode kann nur über eine <xref:System.IConvertible>-Schnittstellenvariable aufgerufen werden, wie im folgenden Beispiel gezeigt. In diesem Beispiel wird ein <xref:System.Int32>-Wert in den entsprechenden <xref:System.Char>-Wert konvertiert.  
  
 [!code-csharp[Conceptual.Conversion#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.conversion/cs/iconvertible1.cs#7)]
 [!code-vb[Conceptual.Conversion#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.conversion/vb/iconvertible1.vb#7)]  
  
 Durch die Anforderung, die Konvertierungsmethode für die Schnittstelle statt für den Implementierungstyp aufzurufen, werden explizite Schnittstellenimplementierungen relativ kostenintensiv. Stattdessen wird für die Konvertierung zwischen Common Language Runtime-Basistypen empfohlen, den entsprechenden Member der <xref:System.Convert>-Klasse aufzurufen. Weitere Informationen finden Sie im folgenden Abschnitt [Die Convert-Klasse](#the-convert-class).  
  
> [!NOTE]
> Zusätzlich zu der Schnittstelle <xref:System.IConvertible> und der Klasse <xref:System.Convert>, die von .NET bereitgestellt werden, stellen einzelne Sprachen eventuell ebenfalls Möglichkeiten zum Durchführen von Konvertierungen bereit. C# verwendet beispielsweise Typumwandlungsoperatoren und Visual Basic im Compiler implementierte Konvertierungsfunktionen wie `CType`, `CInt` und `DirectCast`.  
  
 Für die Unterstützung der Konvertierung zwischen den Basistypen in .NET ist hauptsächlich die Schnittstelle <xref:System.IConvertible> vorgesehen. Die Schnittstelle kann jedoch auch von einem benutzerdefinierten Typ implementiert werden, um die Konvertierung dieses Typs in andere benutzerdefinierte Typen zu unterstützen. Weitere Informationen finden Sie im Abschnitt [Benutzerdefinierte Konvertierungen mit der ChangeType-Methode](#custom-conversions-with-the-changetype-method) weiter unten in diesem Thema.

## <a name="the-convert-class"></a>Die Convert-Klasse

Obwohl die <xref:System.IConvertible>-Schnittstellenimplementierung jedes Basistyps aufgerufen werden kann, um eine Typkonvertierung auszuführen, wird als sprachneutrales Verfahren für die Konvertierung zwischen Basistypen der Aufruf der Methoden der <xref:System.Convert?displayProperty=nameWithType>-Klasse empfohlen. Außerdem kann die <xref:System.Convert.ChangeType%28System.Object%2CSystem.Type%2CSystem.IFormatProvider%29?displayProperty=nameWithType>-Methode verwendet werden, um einen angegebenen benutzerdefinierten Typ in einen anderen Typ zu konvertieren.  
  
### <a name="conversions-between-base-types"></a>Konvertierungen zwischen Basistypen

Die <xref:System.Convert>-Klasse ermöglicht sprachneutrale Konvertierungen zwischen Basistypen, und sie ist für alle Sprachen verfügbar, die für die Common Language Runtime entwickelt wurden. Sie enthält einen vollständigen Satz von Methoden für erweiternde Konvertierungen und für einschränkende Konvertierungen und löst eine <xref:System.InvalidCastException> für Konvertierungen aus, die nicht unterstützt werden (z. B. die Konvertierung eines <xref:System.DateTime>-Werts in einen ganzzahligen Wert). Einschränkende Konvertierungen werden in einem geprüften Kontext ausgeführt, und bei einem Konvertierungsfehler wird eine <xref:System.OverflowException> ausgelöst.  
  
> [!IMPORTANT]
> Da die <xref:System.Convert>-Klasse Methoden für die Konvertierung in jeden Basistyp und von jedem Basistyp enthält, ist es nicht erforderlich, die explizite <xref:System.IConvertible>-Schnittstellenimplementierung jedes Basistyps aufzurufen.  
  
 Im folgenden Beispiel wird veranschaulicht, wie mit der Klasse <xref:System.Convert?displayProperty=nameWithType> verschiedene erweiternde und einschränkende Konvertierungen zwischen .NET-Basistypen ausgeführt werden.  
  
 [!code-csharp[Conceptual.Conversion#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.conversion/cs/convert1.cs#8)]
 [!code-vb[Conceptual.Conversion#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.conversion/vb/convert1.vb#8)]  
  
 In einigen Fällen, insbesondere bei der Konvertierung in Gleitkommawerte und von Gleitkommawerten, ist eine Konvertierung möglicherweise mit einem Genauigkeitsverlust verbunden, obwohl keine <xref:System.OverflowException> ausgelöst wird. Im folgenden Beispiel wird dieser Genauigkeitsverlust veranschaulicht. Im ersten Fall weist ein <xref:System.Decimal>-Wert eine geringere Genauigkeit (weniger signifikante Stellen) auf, wenn er in ein <xref:System.Double> konvertiert wird. Im zweiten Fall wird der <xref:System.Double>-Wert 42,72 auf 43 gerundet, um die Konvertierung durchführen zu können.  
  
 [!code-csharp[Conceptual.Conversion#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.conversion/cs/convert1.cs#9)]
 [!code-vb[Conceptual.Conversion#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.conversion/vb/convert1.vb#9)]  
  
 Eine Tabelle, in der die von der <xref:System.Convert>-Klasse unterstützten Erweiterungskonvertierungen und einschränkenden Konvertierungen aufgeführt sind, finden Sie unter [Typkonvertierungstabellen](conversion-tables.md).  

### <a name="custom-conversions-with-the-changetype-method"></a>Benutzerdefinierte Konvertierungen mit der ChangeType-Methode

Zusätzlich zur Unterstützung von Konvertierungen in die einzelnen Basistypen kann die <xref:System.Convert>-Klasse zum Konvertieren eines benutzerdefinierten Typs in einen oder mehrere vordefinierte Typen verwendet werden. Diese Konvertierung wird von der <xref:System.Convert.ChangeType%28System.Object%2CSystem.Type%2CSystem.IFormatProvider%29?displayProperty=nameWithType>-Methode ausgeführt, die wiederum einen Aufruf der <xref:System.IConvertible.ToType%2A?displayProperty=nameWithType>-Methode des `value`-Parameters umschließt. Dies bedeutet, dass das vom `value`-Parameter dargestellte Objekt eine Implementierung der <xref:System.IConvertible>-Schnittstelle bereitstellen muss.  
  
> [!NOTE]
> Da die Methoden <xref:System.Convert.ChangeType%28System.Object%2CSystem.Type%29?displayProperty=nameWithType> und <xref:System.Convert.ChangeType%28System.Object%2CSystem.Type%2CSystem.IFormatProvider%29?displayProperty=nameWithType> mithilfe eines <xref:System.Type>-Objekts den Zieltyp für die Konvertierung von `value` angeben, können sie verwendet werden, um eine dynamische Konvertierung in ein Objekt auszuführen, dessen Typ zur Kompilierzeit nicht bekannt ist. Beachten Sie jedoch, dass die <xref:System.IConvertible> Implementierung von `value` diese Konvertierung nach wie vor unterstützen muss.  
  
 Im folgenden Beispiel wird eine mögliche Implementierung der <xref:System.IConvertible>-Schnittstelle veranschaulicht, die die Konvertierung eines `TemperatureCelsius`-Objekts in ein `TemperatureFahrenheit`-Objekt und umgekehrt zulässt. Im Beispiel wird die Basisklasse `Temperature` definiert, die die <xref:System.IConvertible>-Schnittstelle implementiert, und die <xref:System.Object.ToString%2A?displayProperty=nameWithType>-Methode wird überschrieben. Die abgeleitete `TemperatureCelsius`-Klasse und die abgeleitete `TemperatureFahrenheit`-Klasse überschreiben jeweils die `ToType`-Methode und die `ToString`-Methode der Basisklasse.  
  
 [!code-csharp[Conceptual.Conversion#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.conversion/cs/iconvertible2.cs#10)]
 [!code-vb[Conceptual.Conversion#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.conversion/vb/iconvertible2.vb#10)]  
  
 Im folgenden Beispiel werden mehrere Aufrufe dieser <xref:System.IConvertible>-Implementierungen zum Konvertieren von `TemperatureCelsius`-Objekten in `TemperatureFahrenheit`-Objekte und umgekehrt veranschaulicht.  
  
 [!code-csharp[Conceptual.Conversion#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.conversion/cs/iconvertible2.cs#11)]
 [!code-vb[Conceptual.Conversion#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.conversion/vb/iconvertible2.vb#11)]  

## <a name="the-typeconverter-class"></a>Die TypeConverter-Klasse

.NET ermöglicht Ihnen das Definieren eines Typkonverters für einen benutzerdefinierten Typ, indem Sie die Klasse <xref:System.ComponentModel.TypeConverter?displayProperty=nameWithType> erweitern und dem Typ über das <xref:System.ComponentModel.TypeConverterAttribute?displayProperty=nameWithType>-Attribut den Typkonverter zuordnen. In der folgenden Tabelle werden die Unterschiede zwischen dieser Vorgehensweise und dem Implementieren der <xref:System.IConvertible>-Schnittstelle für einen benutzerdefinierten Typ hervorgehoben.  
  
> [!NOTE]
> Entwurfszeitunterstützung steht für einen benutzerdefinierten Typ nur zur Verfügung, wenn dieser über einen für ihn definierten Typkonverter verfügt.  
  
|Konvertierung mit TypeConverter|Konvertierung mit IConvertible|  
|------------------------------------|-----------------------------------|  
|Wird für einen benutzerdefinierten Typ implementiert, indem eine separate Klasse von <xref:System.ComponentModel.TypeConverter> abgeleitet wird. Die abgeleitete Klasse wird dem benutzerdefinierten Typ durch Anwenden eines <xref:System.ComponentModel.TypeConverterAttribute>-Attributs zugeordnet.|Wird von einem benutzerdefinierten Typ implementiert, um Konvertierung durchzuführen. Benutzer des Typs rufen eine <xref:System.IConvertible>-Konvertierungsmethode für den Typ auf.|  
|Kann sowohl zur Entwurfszeit als auch zur Laufzeit verwendet werden.|Kann nur zur Laufzeit verwendet werden.|  
|Verwendet Reflektion und ist daher langsamer als die Konvertierung mit <xref:System.IConvertible>.|Verwendet keine Reflektion.|  
|Ermöglicht bidirektionale Typkonvertierungen von benutzerdefinierten Typen in andere Datentypen und umgekehrt. Beispielsweise ermöglicht ein für <xref:System.ComponentModel.TypeConverter> definierter `MyType` Konvertierungen von `MyType` in <xref:System.String> und von <xref:System.String> in `MyType`.|Ermöglicht die Konvertierung von benutzerdefinierten Typen in andere Datentypen, jedoch nicht in umgekehrter Richtung.|  
  
 Weitere Informationen über das Verwenden von Typkonvertern zum Durchführen von Konvertierungen finden Sie unter <xref:System.ComponentModel.TypeConverter?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Convert?displayProperty=nameWithType>
- <xref:System.IConvertible>
- [Typkonvertierungstabellen](conversion-tables.md)
