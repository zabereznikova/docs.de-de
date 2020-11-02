---
title: Allgemeines Typsystem
description: Erkunden Sie das Typsystem in .NET. Erfahren Sie mehr über Typen in .NET (Werttypen oder Verweistypen), Typdefinitionen, Typmember und Merkmale von Typmembern.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- type system
- common type system
- assemblies [.NET], types
- reference types
- value types
- cross-language interoperability
- namespaces [.NET], types
- types, about types
ms.assetid: 53c57c96-83e1-4ee3-9543-9ac832671a89
ms.openlocfilehash: ad42a77f9c6280211902fc4ffbf25871c537baa5
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2020
ms.locfileid: "92889503"
---
# <a name="common-type-system"></a>Allgemeines Typsystem

Das allgemeine Typsystem legt fest, wie Typen in der Common Language Runtime deklariert, verwendet und verwaltet werden. Außerdem ist das System ein wichtiger Bestandteil der Laufzeitunterstützung für die sprachübergreifende Integration. Das allgemeine Typsystem hat die folgenden Funktionen:  
  
- Aufbau eines Frameworks, das die sprachübergreifende Integration, Typsicherheit sowie eine äußerst leistungsfähige Codeausführung ermöglicht.  
  
- Bereitstellung eines objektorientierten Modells, das die vollständige Implementierung zahlreicher Programmiersprachen unterstützt.  
  
- Definition von Regeln, die von Programmiersprachen eingehalten werden müssen und sicherstellen, dass in verschiedenen Sprachen programmierte Objekte miteinander interagieren können.  
  
- Bereitstellung einer Bibliothek, die die bei der Anwendungsentwicklung verwendeten primitiven Datentypen enthält (z. B. <xref:System.Boolean>, <xref:System.Byte>, <xref:System.Char>, <xref:System.Int32> und <xref:System.UInt64>).
  
## <a name="types-in-net"></a>Typen in .NET

 Alle Typen in .NET sind entweder Werttypen oder Verweistypen.  
  
 Werttypen sind Datentypen, deren Objekte durch den tatsächlichen Wert des Objekts dargestellt werden. Wenn einer Variablen eine Instanz eines Werttyps zugewiesen wird, wird dieser Variablen eine neue Kopie des Werts übergeben.  
  
 Referenztypen sind Datentypen, deren Objekte durch einen Verweis (ähnlich einem Zeiger) auf den tatsächlichen Wert des Objekts dargestellt werden. Wenn ein Verweistyp einer Variablen zugeordnet wird, verweist (oder zeigt) diese Variable auf den ursprünglichen Wert. Es wird keine Kopie erstellt.  
  
 Das allgemeine Typsystem in .NET unterstützt die folgenden fünf Typkategorien:  
  
- [Klassen](#classes)  
  
- [Strukturen](#structures)  
  
- [Enumerationen](#enumerations)  
  
- [Schnittstellen](#interfaces)  
  
- [Delegaten](#delegates)  
  
### <a name="classes"></a>Klassen

 Eine Klasse ist ein Referenztyp, der direkt von einer anderen Klasse abgeleitet werden kann und der implizit von <xref:System.Object?displayProperty=nameWithType> abgeleitet ist. Die Klasse definiert die Vorgänge, die ein Objekt (d. h. eine Instanz der Klasse) ausführen kann (Methoden, Ereignisse oder Eigenschaften), sowie die Daten, die das Objekt enthält (Felder). Obwohl eine Klasse im Allgemeinen sowohl Definition als auch Implementierung enthält (im Gegensatz zu Schnittstellen, die z. B. nur eine Definition ohne Implementierung enthalten), kann sie über einen oder mehrere Member ohne Implementierung verfügen.  
  
 In der folgenden Tabelle werden einige Eigenschaften beschrieben, über die eine Klasse verfügen kann. Jede für Laufzeitunterstützung ausgelegte Sprache bietet eine Möglichkeit, eines oder mehrere Merkmale für eine Klasse oder einen Klassenmember festzulegen. In einzelnen Programmiersprachen, die .NET als Ziel haben, sind jedoch möglicherweise nicht alle dieser Eigenschaften verfügbar.  
  
|Merkmal|Beschreibung|  
|--------------------|-----------------|  
|sealed|Legt fest, dass von diesem Typ keine andere Klasse abgeleitet werden kann.|  
|implements|Gibt an, dass die Klasse eine oder mehrere Schnittstellen verwendet; es werden Implementierungen von Schnittstellenmembern bereitgestellt.|  
|abstract|Gibt an, dass die Klasse nicht instanziiert werden kann. Um die Klasse verwenden zu können, müssen Sie eine andere Klasse davon ableiten.|  
|inherits|Legt fest, dass an jeder Stelle, an der die Basisklasse angegeben ist, Instanzen der Klasse verwendet werden können. Eine abgeleitete Klasse, die von einer Basisklasse erbt, kann die Implementierung jedes öffentlichen Members verwenden, der von der Basisklasse bereitgestellt wird, oder die abgeleitete Klasse kann die Implementierung der öffentlichen Member mit einer eigenen Implementierung überschreiben.|  
|exported oder not exported|Gibt an, ob eine Klasse außerhalb der Assembly, in der sie definiert wurde, sichtbar ist. Dieses Merkmal gilt nur für Klassen der obersten Ebene und nicht für geschachtelte Klassen.|  
  
> [!NOTE]
> Eine Klasse kann auch in einer übergeordneten Klasse oder Struktur geschachtelt werden. Auch geschachtelte Klassen verfügen über Membermerkmale. Weitere Informationen finden Sie unter [Geschachtelte Typen](#nested-types).  
  
 Klassenmember, die keine Implementierung haben, sind abstrakte Member. Eine Klasse mit einem oder mehreren abstrakten Membern ist selbst abstrakt, und von dieser Klasse können keine Instanzen erstellt werden. Bei einigen Sprachen, die für die Laufzeit konzipiert sind, können Klassen selbst dann als abstrakt gekennzeichnet werden, wenn sie keine abstrakten Member haben. Sie können eine abstrakte Klasse verwenden, um eine gewisse Basisfunktionalität einzuschließen, die von abgeleiteten Klassen ggf. geerbt bzw. überschrieben werden kann. Nicht abstrakte Klassen werden als konkrete Klassen bezeichnet.  
  
 Eine Klasse kann eine beliebige Anzahl von Schnittstellen implementieren, sie kann jedoch nur von einer Basisklasse neben <xref:System.Object?displayProperty=nameWithType> erben. Hiervon erben alle Klassen implizit. Alle Klassen müssen über mindestens einen Konstruktor verfügen, durch den neue Instanzen der Klasse initialisiert werden. Wenn Sie nicht explizit einen Konstruktor definieren, stellen die meisten Compiler automatisch einen parameterlosen Konstruktor bereit.  
  
### <a name="structures"></a>Strukturen

 Eine Struktur ist ein Werttyp, der implizit von <xref:System.ValueType?displayProperty=nameWithType> abgeleitet ist. Dies ist wiederum von <xref:System.Object?displayProperty=nameWithType> abgeleitet. Eine Struktur ist hilfreich beim Darstellen von Werten mit geringen Arbeitsspeicheranforderungen und beim Übergeben von Werten über Parameter als Wert an Methoden mit stark typisierten Parametern. In .NET werden alle primitiven Datentypen (<xref:System.Boolean>, <xref:System.Byte>, <xref:System.Char>, <xref:System.DateTime>, <xref:System.Decimal>, <xref:System.Double>, <xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.SByte>, <xref:System.Single>, <xref:System.UInt16>, <xref:System.UInt32> und <xref:System.UInt64>) als Strukturen definiert.  
  
 Wie Klassen definieren Strukturen sowohl Daten (die Felder der Struktur) als auch die Vorgänge, die für diese Daten (die Methoden der Struktur) ausgeführt werden können. Dies bedeutet, dass Sie Methoden für Strukturen aufrufen können, einschließlich der für die <xref:System.Object?displayProperty=nameWithType>-Klasse und die <xref:System.ValueType?displayProperty=nameWithType>-Klasse definierten virtuellen Methoden sowie aller Methoden, die für den Werttyp selbst definiert wurden. Anders ausgedrückt können Strukturen Felder, Eigenschaften und Ereignisse sowie statische und nicht statische Methoden aufweisen. Sie können Instanzen von Strukturen erstellen, diese als Parameter übergeben, als lokale Variablen speichern oder im Feld eines anderen Werttyps oder Verweistyps speichern. Strukturen können auch Schnittstellen implementieren.  
  
 Werttypen unterscheiden sich in mehreren Punkten auch von Klassen. Zunächst können sie nicht direkt von einem Typ erben, obwohl sie implizit von <xref:System.ValueType?displayProperty=nameWithType> erben. Ebenso sind alle Werttypen versiegelt, was bedeutet, dass kein anderer Typ von ihnen abgeleitet werden kann. Außerdem benötigen sie keine Konstruktoren.  
  
 Die Common Language Runtime stellt für jeden Werttyp einen entsprechenden geschachtelten Werttyp bereit, der eine Klasse darstellt, die denselben Zustand und dasselbe Verhalten wie der Werttyp aufweist. Eine Instanz eines Werttyps wird beim Übergeben an eine Methode geschachtelt, die einen Parameter vom Typ <xref:System.Object?displayProperty=nameWithType> annimmt. Sie wird mittels Unboxing konvertiert (d. h. aus einer Instanz einer Klasse zurück in die Instanz eines Werttyps konvertiert), wenn ein Steuerelement aus einem Methodenaufruf zurückgegeben wird, in dem ein Werttyp als Parameter als Verweis angenommen wird. In einigen Sprachen muss eine spezielle Syntax verwendet werden, wenn ein mittels Boxing gepackter Typ erforderlich ist; in anderen Sprachen wird der mittels Boxing gepackte Typ bei Bedarf automatisch verwendet. Die Definition eines Werttyps schließt sowohl den mittels Boxing gepackten als auch den mittels Unboxing entpackten Typ ein.  
  
### <a name="enumerations"></a>Enumerationen

 Eine Enumeration ist ein Werttyp, der direkt von <xref:System.Enum?displayProperty=nameWithType> erbt und alternative Namen für die Werte eines zugrunde liegenden primitiven Typs bereitstellt. Ein Enumerationstyp verfügt über einen Namen, einen zugrunde liegenden Typ, bei dem es sich um einen der integrierten Ganzzahltypen mit oder ohne Vorzeichen handeln muss (z. B. <xref:System.Byte>, <xref:System.Int32> oder <xref:System.UInt64>), und einen Satz von Feldern. Die Felder sind statische Literalfelder, von denen jedes eine Konstante darstellt. Derselbe Wert kann auch mehreren Feldern zugewiesen werden. In dieser Situation muss einer der Werte als primärer Enumerationswert für die Reflektion und Zeichenfolgenkonvertierung gekennzeichnet werden.  
  
 Sie können einer Enumeration einen Wert des zugrunde liegenden Typs zuweisen und umgekehrt (für die Laufzeit ist keine Typumwandlung erforderlich). Sie können eine Instanz einer Enumeration erstellen und die Methoden von <xref:System.Enum?displayProperty=nameWithType> sowie alle für den zugrunde liegenden Enumerationstyp definierten Methoden aufrufen. In einigen Sprachen ist es jedoch möglicherweise nicht zulässig, dass eine Enumeration als Parameter übergeben wird, wenn eine Instanz des zugrunde liegenden Typs erforderlich ist (oder umgekehrt).  
  
 Für Enumerationen gelten die folgenden zusätzlichen Beschränkungen:  
  
- Sie können keine eigenen Methoden definieren.  
  
- Sie können keine Schnittstellen implementieren.  
  
- Sie können keine Eigenschaften oder Ereignisse definieren.  
  
- Sie können nicht generisch sein, es sei denn, sie sind nur deshalb generisch, weil sie in einem generischen Typ geschachtelt sind. Das bedeutet, dass eine Enumeration nicht über eigene Typparameter verfügen kann.  
  
    > [!NOTE]
    > Geschachtelte Typen (z. B. Enumerationen), die mit Visual Basic, C# oder C++ erstellt wurden, enthalten die Typparameter aller einschließenden generischen Typen und sind daher generisch, auch wenn sie über keine eigenen Typparameter verfügen. Weitere Informationen finden Sie im Referenzthema <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> unter "Geschachtelte Typen".  
  
 Durch das <xref:System.FlagsAttribute>-Attribut wird eine spezielle Art von Enumeration, das so genannte Bitfeld, ausgewiesen. Von der Laufzeit selbst wird nicht zwischen herkömmlichen Enumerationen und Bitfeldern unterschieden, in Ihrer Programmiersprache könnte dies jedoch der Fall sein. Wird diese Unterscheidung getroffen, können zum Generieren nicht benannter Werte zwar bitweise Operatoren für Bitfelder, jedoch nicht für Enumerationen verwendet werden. Enumerationen werden im Allgemeinen für Listen eindeutiger Elemente verwendet, z. B. für Wochentage bzw. Namen für Regionen oder Länder usw. Bitfelder werden in der Regel für Listen verwendet, in denen Qualitätsmerkmale oder Mengen definiert sind, die kombiniert auftreten können, z. B. `Red And Big And Fast`.  
  
 Das folgende Beispiel zeigt, wie Bitfelder und herkömmliche Enumerationen in Kombination verwendet werden können.  
  
 [!code-csharp[Conceptual.Types.Enum#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.enum/cs/example.cs#1)]
 [!code-vb[Conceptual.Types.Enum#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.enum/vb/example.vb#1)]  

### <a name="interfaces"></a>Schnittstellen

 Eine Schnittstelle definiert einen Vertrag, der eine Kann-Beziehung oder eine Hat-ein-Beziehung angibt. Schnittstellen werden häufig zur Implementierung einer Funktionalität verwendet, z. B. Vergleichen und Sortieren (die <xref:System.IComparable>- und <xref:System.IComparable%601>-Schnittstellen), Testen auf Gleichheit (die <xref:System.IEquatable%601>-Schnittstelle) oder Auflistung von Elementen in einer Sammlung (die <xref:System.Collections.IEnumerable>- und <xref:System.Collections.Generic.IEnumerable%601>-Schnittstellen). Schnittstellen können Eigenschaften, Methoden und Ereignisse aufweisen, die alle abstrakte Member sind. Während die Schnittstelle die Member und deren Signaturen definiert, definiert der die Schnittstelle implementierende Typ die Funktionalität der Schnittstellenmember. Dies bedeutet, dass jede Klasse oder Struktur, die eine Schnittstelle implementiert, Definitionen für die in der Schnittstelle deklarierten abstrakten Member bereitstellen muss. Für eine Schnittstelle kann es erforderlich sein, dass eine beliebige implementierende Klasse oder Struktur auch mindestens eine andere Schnittstelle implementiert.  
  
 Für Schnittstellen gelten die folgenden Beschränkungen:  
  
- Eine Schnittstelle kann mit beliebigem Zugriff deklariert werden, die Schnittstellenmember müssen jedoch alle über die Zugriffsart public verfügen.  
  
- Schnittstellen können keine Konstruktoren definieren.  
  
- Schnittstellen können keine Felder definieren.  
  
- Schnittstellen können nur Instanzmember definieren. Sie können keine statischen Member definieren.  
  
 Jede Sprache muss Regeln zur Verfügung stellen, mit deren Hilfe eine Implementierung der Schnittstelle zugeordnet werden kann, die den Member benötigt. Der Grund ist, dass in mehreren Schnittstellen Member mit identischen Signaturen deklariert werden können, die jedoch möglicherweise über separate Implementierungen verfügen.  

### <a name="delegates"></a>Delegaten

 Delegaten sind Verweistypen, die einen ähnlichen Zweck erfüllen wie Funktionszeiger in C++. Sie werden für Ereignishandler und Rückruffunktionen in .NET verwendet. Im Gegensatz zu Funktionszeigern sind Delegaten sicher, überprüfbar und typsicher. Ein Delegattyp kann jede Instanzmethode oder statische Methode darstellen, die über eine kompatible Signatur verfügt.  
  
 Ein Parameter eines Delegaten ist mit dem entsprechenden Parameter einer Methode kompatibel, wenn der Typ des Delegatenparameters restriktiver ist als der Methodenparameter, da so gewährleistet ist, dass ein an den Delegaten übergebenes Argument problemlos an die Methode weitergeleitet werden kann.  
  
 Ebenso ist der Rückgabetyp eines Delegaten kompatibel mit dem Rückgabetyp einer Methode, wenn der Rückgabetyp der Methode restriktiver ist als der Rückgabetyp des Delegaten, da so gewährleistet ist, dass der Rückgabewert der Methode problemlos in den Rückgabetyp des Delegaten umgewandelt werden kann.  
  
 Beispielsweise kann ein Delegat mit dem Parametertyp <xref:System.Collections.IEnumerable> und dem Rückgabetyp <xref:System.Object> eine Methode mit dem Parametertyp <xref:System.Object> und dem Rückgabetyp <xref:System.Collections.IEnumerable> darstellen. Weitere Informationen und Beispielcode finden Sie unter <xref:System.Delegate.CreateDelegate%28System.Type%2CSystem.Object%2CSystem.Reflection.MethodInfo%29?displayProperty=nameWithType>.  
  
 Ein Delegat wird als gebunden an die Methode bezeichnet, die er darstellt. Ein Delegat kann nicht nur an die Methode, sondern auch an ein Objekt gebunden sein. Das Objekt stellt den ersten Parameter der Methode dar und wird jedes Mal an die Methode übergeben, wenn der Delegat aufgerufen wird. Wenn es sich bei der Methode um eine Instanzmethode handelt, wird das gebundene Objekt als impliziter `this`-Parameter (`Me` in Visual Basic) übergeben. Wenn die Methode statisch ist, wird das Objekt als erster formaler Parameter der Methode übergeben, und die Delegatsignatur muss den verbleibenden Parametern entsprechen. Weitere Informationen und Beispielcode finden Sie unter <xref:System.Delegate?displayProperty=nameWithType>.  
  
 Alle Delegaten erben von <xref:System.MulticastDelegate?displayProperty=nameWithType>, welcher von <xref:System.Delegate?displayProperty=nameWithType> erbt. In den Programmiersprachen C#, Visual Basic und C++ ist die Vererbung von diesen Typen nicht zulässig. Stattdessen werden Schlüsselwörter zum Deklarieren von Delegaten bereitgestellt.  
  
 Da Delegaten von <xref:System.MulticastDelegate> erben, verfügt ein Delegat über eine Aufrufliste. Dabei handelt es sich um eine Liste der Methoden, die dieser Delegat darstellt und die beim Aufrufen des Delegaten ausgeführt werden. Alle Methoden in der Liste empfangen die beim Aufrufen des Delegaten angegebenen Argumente.  
  
> [!NOTE]
> Der Rückgabewert von Delegaten mit mehr als einer Methode in der Aufrufliste ist nicht definiert, selbst wenn diese über einen Rückgabetyp verfügen.  
  
 In vielen Fällen (z. B. bei Rückrufmethoden) stellt ein Delegat nur eine Methode dar. Sie müssen den Delegaten lediglich erstellen und aufrufen.  
  
 Für Delegaten, die mehrere Methoden darstellen, enthält .NET Methoden der <xref:System.Delegate>-Delegatklasse und <xref:System.MulticastDelegate>-Delegatklasse, um verschiedene Vorgänge zu unterstützen. Dazu gehören das Hinzufügen einer Methode zur Aufrufliste eines Delegaten (die <xref:System.Delegate.Combine%2A?displayProperty=nameWithType>-Methode), das Entfernen einer Methode (die <xref:System.Delegate.Remove%2A?displayProperty=nameWithType>-Methode) und das Abrufen der Aufrufliste (die <xref:System.Delegate.GetInvocationList%2A?displayProperty=nameWithType>-Methode).  
  
> [!NOTE]
> Es ist in C#, C++ und Visual Basic nicht erforderlich, diese Methoden für Ereignishandlerdelegaten einzusetzen, da in diesen Programmiersprachen Syntax zum Hinzufügen und Entfernen von Ereignishandlern bereitsteht.  

## <a name="type-definitions"></a>Typdefinitionen

 Eine Typdefinition enthält Folgendes:  
  
- Alle für den Typ definierten Attribute.  
  
- Den Zugriff des Typs (Sichtbarkeit).  
  
- Den Typnamen.  
  
- Den Basistyp des Typs.  
  
- Alle durch den Typ implementierten Schnittstellen.  
  
- Definitionen für jeden Member des Typs.  
  
### <a name="attributes"></a>Attribute  
 Durch Attribute werden zusätzliche benutzerdefinierte Metadaten bereitgestellt. Sie werden in dem meisten Fällen verwendet, um zusätzliche Informationen zu einem Typ in seiner Assembly zu speichern oder um das Verhalten eines Typmembers zur Entwurfszeit oder in der Laufzeitumgebung zu ändern.  
  
 Attribute sind selbst Klassen, die von <xref:System.Attribute?displayProperty=nameWithType> erben. Sprachen, die die Verwendung von Attributen unterstützen, verfügen über eine eigene Syntax zum Anwenden von Attributen auf ein Sprachelement. Attribute können auf fast alle Sprachelemente angewendet werden. Die einzelnen Elemente, auf die ein Attribut angewendet werden kann, werden vom auf die Attributklasse angewendeten <xref:System.AttributeUsageAttribute> definiert.  
  
### <a name="type-accessibility"></a>Typzugriff  
 Alle Typen verfügen über einen Modifizierer, der regelt, welche anderen Typen auf diesen Typ zugreifen können. In der folgenden Tabelle werden die von der Laufzeit unterstützten Zugriffsarten auf Typen beschrieben.  
  
|Zugriff|Beschreibung|  
|-------------------|-----------------|  
|public|Auf diesen Typ kann von allen Assemblys zugegriffen werden.|  
|Assembly|Auf diesen Typ kann nur innerhalb seiner Assembly zugegriffen werden.|  
  
 Der Zugriff auf einen geschachtelten Typ hängt von seiner Zugriffsdomäne ab, die sowohl durch den deklarierten Zugriffstyp des Members als auch durch die Zugriffsdomäne des direkt enthaltenden Typs bestimmt wird. Die Zugriffsdomäne eines geschachtelten Typs kann jedoch nicht über die des enthaltenden Typs hinausgehen.  
  
 Die Zugriffsdomäne eines geschachtelten Members `M`, der in einem Typ `T` innerhalb eines Programms `P` deklariert ist, wird wie folgt definiert (wobei `M` selbst ein Typ sein kann):  
  
- Wenn die deklarierte Zugriffsart von `M` den Wert `public` hat, entspricht die Zugriffsdomäne von `M` der von `T`.  
  
- Wenn die deklarierte Zugriffsart von `M` den Wert `protected internal` hat, entspricht die Zugriffsdomäne von `M` der Schnittmenge zwischen der Zugriffsdomäne von `T`, dem Programmtext von `P` und dem Programmtext jedes Typs, der von `T` abgeleitet und außerhalb von `P` deklariert wurde.  
  
- Wenn die deklarierte Zugriffsart von `M` den Wert `protected` hat, entspricht die Zugriffsdomäne von `M` der Schnittmenge zwischen der Zugriffsdomäne von `T`, dem Programmtext von `T` und jedem von `T` abgeleiteten Typ.  
  
- Wenn die deklarierte Zugriffsart von `M` den Wert `internal` hat, entspricht die Zugriffsdomäne von `M` der Schnittmenge zwischen der Zugriffsdomäne von `T` und dem Programmtext von `P`.  
  
- Wenn die deklarierte Zugriffsart von `M` den Wert `private` hat, entspricht die Zugriffsdomäne von `M` dem Programmtext von `T`.  
  
### <a name="type-names"></a>Typnamen  
 Das allgemeine Typsystem sieht lediglich zwei Namenseinschränkungen vor:  
  
- Alle Namen werden als Unicode-Zeichenfolgen (16-Bit-Zeichen) codiert.  
  
- Ein eingebetteter Wert von 0x0000 (16 Bits) ist für Namen nicht zulässig.  
  
 In den meisten Sprachen gelten jedoch möglicherweise zusätzliche Beschränkungen für Typnamen. Alle Vergleiche erfolgen byteweise, sie berücksichtigen daher die Groß-/Kleinschreibung und sind unabhängig vom Gebietsschema.  
  
 Obwohl ein Typ auf Typen aus anderen Modulen und Assemblys verweisen kann, muss er vollständig innerhalb eines .NET-Moduls definiert werden. (Abhängig von der Compilerunterstützung kann er jedoch auf mehrere Quellcodedateien aufgeteilt werden.) Typnamen müssen nur innerhalb eines Namespace eindeutig sein. Um einen Typ vollständig zu identifizieren, muss der Typname durch den Namespace gekennzeichnet werden, die die Typimplementierung enthält.  
  
### <a name="base-types-and-interfaces"></a>Basistypen und Schnittstellen  
 Ein Typ kann Werte und Verhaltensdefinitionen von anderen Typen erben. Gemäß dem allgemeinen Typsystem können Typen nicht von mehr als einem Basistyp erben.  
  
 Ein Typ kann eine beliebige Anzahl von Schnittstellen implementieren. Zur Implementierung einer Schnittstelle muss ein Typ alle virtuellen Member der betreffenden Schnittstelle implementieren. Eine virtuelle Methode kann durch einen abgeleiteten Typ implementiert und entweder statisch oder dynamisch aufgerufen werden.  

## <a name="type-members"></a>Typmember

 Die Laufzeit ermöglicht es Ihnen, Member des Typs zu definieren. Hierbei werden das Verhalten und der Zustand eines Typs angegeben. Typmember umfassen Folgendes:  
  
- [Felder](#fields)  
  
- [Eigenschaften](#properties)  
  
- [Methoden](#methods)  
  
- [Konstruktoren](#constructors)  
  
- [Ereignisse](#events)  
  
- [Geschachtelte Typen](#nested-types)  

### <a name="fields"></a>Felder

 Ein Feld beschreibt und enthält Teile des Typzustands. Felder können jedem von der Laufzeit unterstützten Typ entsprechen. In den meisten Fällen sind Felder `private` oder `protected`, damit auf sie nur innerhalb der Klasse oder aus einer abgeleiteten Klasse zugegriffen werden kann. Wenn der Wert eines Felds außerhalb seines Typs geändert werden kann, wird normalerweise ein Eigenschaftensatzaccessor verwendet. Öffentlich verfügbar gemachte Felder sind normalerweise schreibgeschützt und können zwei Typen aufweisen:  
  
- Konstanten, deren Wert zur Entwurfszeit zugewiesen wird. Diese sind statische Member einer Klasse, obwohl sie nicht mit dem `static`-Schlüsselwort (`Shared` in Visual Basic) definiert werden.  
  
- Schreibgeschützte Variablen, deren Werte im Klassenkonstruktor zugewiesen werden können.  
  
 Im folgenden Beispiel werden diese zwei Verwendungen für schreibgeschützte Felder veranschaulicht.  
  
 [!code-csharp[Conceptual.Types.Members.Fields#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.members.fields/cs/example.cs#1)]
 [!code-vb[Conceptual.Types.Members.Fields#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.members.fields/vb/example.vb#1)]  

### <a name="properties"></a>Eigenschaften

 Eine Eigenschaft benennt einen Wert oder Zustand des Typs und definiert Methoden zum Abrufen oder Festlegen des Eigenschaftswerts. Eigenschaften können primitive Typen, Auflistungen primitiver Typen, benutzerdefinierte Typen oder Auflistungen benutzerdefinierter Typen sein. Eigenschaften werden häufig verwendet, um die Unabhängigkeit der öffentlichen Schnittstelle eines Typs von seiner tatsächlichen Darstellung zu gewährleisten. So können Eigenschaften Werte reflektieren, die nicht direkt in der Klasse gespeichert sind (z. B., wenn eine Eigenschaft einen berechneten Wert zurückgibt), oder eine Validierung ausführen, bevor privaten Feldern Werte zugewiesen werden. Im folgenden Codebeispiel wird das zweite Schema veranschaulicht.  
  
 [!code-csharp[Conceptual.Types.Members.Properties#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.members.properties/cs/example.cs#1)]
 [!code-vb[Conceptual.Types.Members.Properties#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.members.properties/vb/example.vb#1)]  
  
 Die Microsoft Intermediate Language (MSIL) schließt nicht nur die Eigenschaft ein, sondern für einen Typ mit einer lesbaren Eigenschaft darüber hinaus eine `get_`*Eigenschaftsname* -Methode und für einen Typ mit einer beschreibbaren Eigenschaft eine `set_`*Eigenschaftsname* -Methode.  

### <a name="methods"></a>Methoden

 Eine Methode beschreibt Vorgänge, die für den Typ verfügbar sind. Eine Methodensignatur gibt die zulässigen Typen aller Parameter sowie des Rückgabewerts der Methode an.  
  
 Obwohl die meisten Methoden die erforderliche Anzahl von Parametern für Methodenaufrufe genau definieren, unterstützen einige Methoden eine variable Anzahl von Parametern. Der letzte deklarierte Parameter dieser Methoden wird mit dem <xref:System.ParamArrayAttribute>-Attribut markiert. Sprachcompiler stellen in der Regel ein Schlüsselwort bereit, z. B. `params` in C# und `ParamArray` in Visual Basic, das die explizite Verwendung von <xref:System.ParamArrayAttribute> unnötig macht.  

### <a name="constructors"></a>Konstruktoren

 Ein Konstruktor ist eine spezielle Methodenform, durch die neue Instanzen einer Klasse oder Struktur erstellt werden. Wie jede andere Methode kann ein Konstruktor Parameter einschließen. Konstruktoren verfügen jedoch nicht über einen Rückgabewert (d. h., sie geben `void` zurück).  
  
 Wenn der Quellcode für eine Klasse nicht explizit einen Konstruktor definiert, schließt der Compiler einen parameterlosen Konstruktor ein. Wenn der Quellcode für eine Klasse jedoch nur parametrisierte Konstruktoren definiert, generieren der Visual Basic-Compiler und der C#-Compiler keinen parameterlosen Konstruktor.  
  
 Wenn der Quellcode für eine Struktur Konstruktoren definiert, müssen diese parametrisiert werden. Eine Struktur kann keinen parameterlosen Konstruktor definieren, und Compiler generieren keine parameterlosen Konstruktoren für Strukturen oder andere Werttypen. Alle Werttypen verfügen über einen impliziten parameterlosen Konstruktor. Dieser Konstruktor wird von der Common Language Runtime implementiert und initialisiert alle Felder der Struktur mit ihren Standardwerten.  

### <a name="events"></a>Ereignisse

 Ein Ereignis definiert ein Ereignis, auf das reagiert werden kann, und definiert Methoden, mit denen das Ereignis ausgelöst und abonniert bzw. sein Abonnement aufgehoben werden kann. Häufig werden mithilfe von Ereignissen andere Typen über Zustandsänderungen informiert. Weitere Informationen finden Sie unter [Ereignisse](../events/index.md).  

### <a name="nested-types"></a>Geschachtelte Typen

 Ein geschachtelter Typ ist ein Typ, der ein Member eines anderen Typs ist. Geschachtelte Typen müssen eng mit dem zugehörigen enthaltenden Typ verknüpft sein und dürfen nicht für allgemeine Zwecke verwendbar sein. Geschachtelte Typen sind sinnvoll, wenn der deklarierende Typ Instanzen des geschachtelten Typs verwendet und erstellt und die Verwendung des geschachtelten Typs nicht in öffentlichen Membern verfügbar gemacht wird.  
  
 Für einige Entwickler sind geschachtelte Typen verwirrend, und sie sollten nur öffentlich sichtbar sein, wenn ein zwingender Grund dafür vorliegt. In einer gut entworfenen Bibliothek sollten Entwickler nur selten geschachtelte Typen zum Instanziieren von Objekten oder Deklarieren von Variablen verwenden müssen.  

## <a name="characteristics-of-type-members"></a>Eigenschaften von Typmembern

 Das allgemeine Typsystem unterstützt Typmember, die eine Vielzahl unterschiedlicher Merkmale haben können. Zur Unterstützung all dieser Merkmale sind jedoch keine speziellen Sprachen erforderlich. In der folgenden Tabelle sind diese Membermerkmale beschrieben.  
  
|Merkmal|Anwendbar auf|Beschreibung|  
|--------------------|------------------|-----------------|  
|abstract|Methoden, Eigenschaften und Ereignisse|Der Typ stellt keine Methodenimplementierung bereit. Typen, die abstrakte Methoden erben oder implementieren, müssen eine Implementierung für die Methode bereitstellen. Die einzige Ausnahme liegt vor, wenn der abgeleitete Typ selbst vom Typ abstract ist. Alle Methoden vom Typ abstract sind auch virtual.|  
|private, family, assembly, family und assembly, family oder assembly oder public|Alle|Definiert die Zugriffsart des Members:<br /><br /> private<br /> Zugriff ist nur innerhalb desselben Typs wie dem des Members oder innerhalb eines geschachtelten Typs möglich.<br /><br /> family<br /> Zugriff innerhalb desselben Typs wie dem des Members und von abgeleiteten Typen möglich, die davon erben.<br /><br /> Assembly<br /> Zugriff nur in der Assembly möglich, in der der Typ definiert ist.<br /><br /> family und assembly<br /> Zugriff nur von Typen möglich, die sowohl über den Zugriffstyp family als auch assembly verfügen.<br /><br /> family oder assembly<br /> Zugriff nur von Typen möglich, die über den Zugriffstyp "family" oder "assembly" verfügen.<br /><br /> public<br /> Zugriff von jedem Typ möglich.|  
|final|Methoden, Eigenschaften und Ereignisse|Die virtuelle Methode kann in einem abgeleiteten Typ nicht überschrieben werden.|  
|initialize-only|Felder|Der Wert kann lediglich initialisiert werden. Nach der Initialisierung ist kein Schreibzugriff möglich.|  
|instance|Felder, Methoden, Eigenschaften und Ereignisse|Wenn ein Member nicht als `static` (C# und C++), `Shared` (Visual Basic), `virtual` (C# und C++) oder `Overridable` (Visual Basic) gekennzeichnet ist, handelt es sich um einen Instanzmember (es ist kein instance-Schlüsselwort vorhanden). Im Arbeitsspeicher befinden sich so viele Kopien dieser Member wie Objekte, von denen sie verwendet werden.|  
|literal|Felder|Der dem Feld zugewiesene Wert ist ein fester, zur Kompilierungszeit bekannter Wert eines integrierten Werttyps. Literalfelder werden zeitweise auch als Konstanten bezeichnet.|  
|newslot oder override|Alle|Definiert, wie der Member mit geerbten Membern interagiert, die dieselbe Signatur haben:<br /><br /> newslot<br /> Geerbte Member mit derselben Signatur werden verdeckt.<br /><br /> override<br /> Ersetzt die Definition einer geerbten virtuellen Methode.<br /><br /> Der Standardwert ist newslot.|  
|static|Felder, Methoden, Eigenschaften und Ereignisse|Der Member gehört dem Typ an, mit dem er definiert wurde, und keiner bestimmten Instanz des Typs. Der Member existiert selbst dann, wenn keine Instanz des Typs erstellt wird, und wird von allen Instanzen des Typs gemeinsam genutzt.|  
|virtual|Methoden, Eigenschaften und Ereignisse|Die Methode kann durch einen abgeleiteten Typ implementiert und entweder statisch oder dynamisch aufgerufen werden. Beim dynamischen Aufruf bestimmt der Typ der Instanz, durch die der Aufruf zur Laufzeit ausgeführt wird (und nicht der zur Kompilierungszeit bekannte Typ), welche Implementierung der Methode aufgerufen wird. Um eine Methode vom Typ virtual statisch aufzurufen, muss die Variable u. U. in einen Typ umgewandelt werden, der die gewünschte Methodenversion verwendet.|  
  
### <a name="overloading"></a>Überladen  
 Jeder Typmember verfügt über eine eindeutige Signatur. Methodensignaturen bestehen aus dem Methodennamen und einer Parameterliste (die Reihenfolge und Typen der Argumente der Methode). Solange die Signaturen unterschiedlich sind, können innerhalb eines Typs mehrere Methoden mit demselben Namen definiert werden. Wenn zwei oder mehrere Methoden mit demselben Namen definiert sind, wird von einer "überladenen" Methode gesprochen. In <xref:System.Char?displayProperty=nameWithType> wird z. B. die <xref:System.Char.IsDigit%2A>-Methode überladen. Eine Methode nimmt einen <xref:System.Char> an. Die andere Methode nimmt einen <xref:System.String> und einen <xref:System.Int32> an.  
  
> [!NOTE]
> Der Rückgabetyp wird nicht als Teil der Signatur einer Methode betrachtet. Dies bedeutet, dass Methoden nicht überladen werden können, wenn sich nur ihr Rückgabetyp unterscheidet.  
  
### <a name="inherit-override-and-hide-members"></a>Erben, Überschreiben und Ausblenden von Membern  
 Ein abgeleiteter Typ erbt alle Member seines Basistyps. Dies bedeutet, dass diese Member für den abgeleiteten Typ definiert und verfügbar sind. Das Verhalten oder die Merkmale geerbter Member können auf zwei Weisen geändert werden:  
  
- Ein abgeleiteter Typ kann einen geerbten Member verdecken, indem er einen neuen Member mit derselben Signatur definiert. Dies kann z. B. geschehen, um einen Member, der zuvor als public deklariert war, als private zu definieren, oder um ein neues Verhalten für eine geerbte Methode zu definieren, die mit `final` gekennzeichnet ist.  
  
- Ein abgeleiteter Typ kann eine geerbte virtuelle Methode überschreiben. Die überschreibende Methode stellt eine neue Definition für die Methode bereit, die basierend auf dem Werttyp zur Laufzeit aufgerufen wird und nicht basierend auf dem zur Kompilierungszeit bekannten Variablentyp. Eine virtuelle Methode kann nur von einer Methode überschrieben werden, wenn die virtuelle Methode nicht als `final` gekennzeichnet ist und die neue Methode mindestens dieselben Zugriffstypen unterstützt wie die virtuelle Methode.  
  
## <a name="see-also"></a>Siehe auch

- [.NET API-Browser](../../../api/index.md)
- [Übersicht: Common Language Runtime (CLR)](../clr.md)
- [Typkonvertierung in .NET](type-conversion.md)
