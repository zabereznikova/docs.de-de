---
title: Grundlegende Typen | C#-Handbuch
description: "Erfahren Sie mehr über die grundlegenden Typen (numerische Werte, Zeichenfolgen und Objekte) in allen C#-Programmen"
keywords: .NET, .NET Core, C#
author: stevehoag
ms.author: shoag
ms.date: 10/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 95c686ba-ae4f-440e-8e94-0dbd6e04d11f
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 57c5524a18535778db337500b0a7e9013ce93519
ms.lasthandoff: 03/13/2017

---

# <a name="types-variables-and-values"></a>Typen, Variablen und Werte  
C# ist eine stark typisierte Sprache. Jede Variable und jede Konstante verfügt über einen Typ, genau wie jeder Ausdruck, der zu einem Wert ausgewertet wird. Jede Methodensignatur gibt für jeden Eingabeparameter und den Rückgabewert einen Typ an. In der .NET Framework-Klassenbibliothek sind integrierte numerische Typen sowie komplexere Typen definiert, die eine große Anzahl logischer Konstrukte darstellen, z. B. das Dateisystem, Netzwerkverbindungen, Auflistungen und Arrays von Objekten sowie Datumsangaben. In einem typischen C#-Programm werden Typen aus der Klassenbibliothek sowie benutzerdefinierte Typen verwendet, die die Konzepte für das Problemfeld des Programms modellieren.  
  
Folgende Informationen können in einem Typ gespeichert sein:  
  
-   Der Speicherplatz, den eine Variable des Typs erfordert  
  
-   Die maximalen und minimalen Werte, die diese darstellen kann  
  
-   Die enthaltenen Member (Methoden, Felder, Ereignisse usw.)  
  
-   Der Basistyp, von dem geerbt wird  
  
-   Die Position, an der der Arbeitsspeicher für Variablen zur Laufzeit belegt wird  
  
-   Die Arten von zulässigen Vorgängen  
  
Der Compiler verwendet Typinformationen, um sicherzustellen, dass alle im Code ausgeführten Vorgänge *typsicher* sind. Wenn Sie z.B. eine Variable vom Typ [int](https://msdn.microsoft.com/library/5kzh1b5w.aspx) deklarieren, können Sie mit dem Compiler die Variable für Additions- und Subtraktionsvorgänge verwenden. Wenn Sie dieselben Vorgänge für eine Variable vom Typ [bool](https://msdn.microsoft.com/library/c8f5xwh7.aspx) ausführen möchten, generiert der Compiler einen Fehler, wie im folgenden Beispiel dargestellt:  
  
[!code-csharp[Typsicherheit](../../samples/snippets/csharp/concepts/basic-types/type-safety.cs)]  
  
> [!NOTE]  
>  C- und C++-Entwickler sollten beachten, dass in C# [bool](https://msdn.microsoft.com/library/c8f5xwh7.aspx) nicht in [int](https://msdn.microsoft.com/library/5kzh1b5w.aspx) konvertiert werden kann.  
  
Der Compiler bettet die Typinformationen als Metadaten in die ausführbare Datei ein. Die Common Language Runtime (CLR) verwendet diese Metadaten zur Laufzeit, um die Typsicherheit zu gewährleisten, wenn Speicherplatz belegt und freigegeben wird.  

## <a name="specifying-types-in-variable-declarations"></a>Angeben von Typen in Variablendeklarationen  
Wenn Sie eine Variable oder Konstante in einem Programm deklarieren, müssen Sie den Typ festlegen oder das [var](https://msdn.microsoft.com/library/bb383973.aspx)-Schlüsselwort verwenden, damit der Typ vom Compiler abgeleitet wird. Im folgenden Beispiel werden einige Variablendeklarationen dargestellt, die sowohl integrierte numerische Typen als auch komplexe benutzerdefinierte Typen verwenden:  
  
[!code-csharp[Variablendeklaration](../../samples/snippets/csharp/concepts/basic-types/variable-declaration.cs)]  
  
Die Methodenparameter- und Rückgabewerttypen werden in der Methodensignatur angegeben. Die folgende Signatur zeigt eine Methode, für die eine [int](https://msdn.microsoft.com/library/5kzh1b5w.aspx) als Eingabeargument benötigt wird und die eine Zeichenfolge zurückgibt:  
  
[!code-csharp[Methodensignatur](../../samples/snippets/csharp/concepts/basic-types/method-signature.cs)]  
  
Nachdem eine Variable deklariert wurde, kann sie nicht erneut mit einem neuen Typ deklariert werden. Außerdem kann ihr kein Wert zugewiesen werden, der nicht mit dem deklarierten Typ kompatibel ist. Zum Beispiel können Sie nicht eine [int](https://msdn.microsoft.com/library/5kzh1b5w.aspx) deklarieren und dieser dann den booleschen Wert [true](https://msdn.microsoft.com/library/06d3w013.aspx) zuweisen. Werte können jedoch in andere Typen konvertiert werden, z. B., wenn diese neuen Variablen zugewiesen oder als Methodenargumente übergeben werden. Eine *Typkonvertierung*, die keinen Datenverlust verursacht, wird automatisch vom Compiler ausgeführt. Eine Konvertierung, die möglicherweise Datenverlust verursacht, erfordert eine *Umwandlung* in den Quellcode. 

Weitere Informationen finden Sie unter [Umwandlung und Typkonvertierungen](https://msdn.microsoft.com/library/ms173105.aspx).
 
## <a name="built-in-types"></a>Integrierte Typen
C# liefert einen Standardsatz mit integrierten numerischen Typen zur Darstellung von ganzen Zahlen, Gleitkommawerten, booleschen Ausdrücken, Textzeichen, Dezimalwerten und anderen Datentypen. Es gibt auch integrierte **Zeichenfolgen**- und **Objekt**-Typen. Diese können Sie in jedem C#-Programm verwenden. Weitere Informationen über die integrierten Typen finden Sie unter [Typenverweistabellen](https://msdn.microsoft.com/library/1dhd7f2x.aspx).  
  
## <a name="custom-types"></a>Benutzerdefinierte Typen  
Sie können die Konstrukte [struct](https://msdn.microsoft.com/library/ah19swz4.aspx), [class](https://msdn.microsoft.com/library/0b0thckt.aspx), [interface](https://msdn.microsoft.com/library/87d83y5b.aspx) und [enum](https://msdn.microsoft.com/library/sbbt4032.aspx) verwenden, um eigene benutzerdefinierte Typen zu erstellen. Die .NET Framework-Klassenbibliothek ist eine Auflistung benutzerdefinierter, von Microsoft bereitgestellter Typen, die Sie in Ihren eigenen Anwendungen verwenden können. Standardmäßig sind die am häufigsten verwendeten Typen in der Klassenbibliothek in jedem C#-Programm verfügbar. Andere stehen nur zur Verfügung, wenn Sie ausdrücklich einen Projektverweis auf die Assembly hinzufügen, in der diese definiert sind. Wenn der Compiler über einen Verweis auf die Assembly verfügt, können Sie Variablen (und Konstanten) des in dieser Assembly deklarierten Typs im Quellcode deklarieren. Weitere Informationen finden Sie in der Dokumentation zur [.NET Framework-Klassenbibliothek](https://msdn.microsoft.com/library/gg145045(v=vs.110).aspx).  
  
## <a name="generic-types"></a>Generische Typen  
Ein Typ kann mit einem oder mehreren *Typparametern* deklariert werden, die als Platzhalter für den eigentlichen Typ verwendet werden (den *konkreten Typ*), der vom Clientcode beim Erstellen einer Instanz des Typs bereitgestellt wird. Solche Typen werden als *generische Typen* bezeichnet. Beispielsweise besitzt der .NET Framework-Typ @System.Collections.Generic.List%601 einen Typparameter, dem üblicherweise der Name *T* gegeben wird. Beim Erstellen einer Instanz des Typs geben Sie die Objekte an, die die Liste enthalten soll, z. B. string:  
  
[!code-csharp[Generische Typen](../../samples/snippets/csharp/concepts/basic-types/generic-type.cs)] 
  
Die Verwendung des Typparameters ermöglicht die Wiederverwendung derselben Klasse für beliebige Elementtypen, ohne die einzelnen Elemente in [object](https://msdn.microsoft.com/library/9kkx3h3c.aspx) konvertieren zu müssen. Generische Auflistungsklassen werden als *stark typisierte Auflistungen* bezeichnet, weil der Compiler den jeweiligen Typ der Elemente in der Auflistung kennt und zur Kompilierzeit einen Fehler auslösen kann, wenn Sie beispielsweise versuchen, dem `strings`-Objekt im vorherigen Beispiel eine ganze Zahl hinzuzufügen. Weitere Informationen finden Sie unter [Generika](programming-guide/generics/index.md). 

## <a name="implicit-types-anonymous-types-and-tuple-types"></a>Implizite Typen, anonyme Typen und Tupel-Typen  
Wie bereits zuvor erläutert, können Sie eine lokale Variable (jedoch keine Klassenmember) implizit eingeben, indem Sie das [var](https://msdn.microsoft.com/library/bb383973.aspx)-Schlüsselwort verwenden. Die Variable erhält weiterhin zur Kompilierzeit einen Typ, aber der Typ wird vom Compiler bereitgestellt. Weitere Informationen finden Sie unter [Implizit typisierte lokale Variablen](https://msdn.microsoft.com/library/bb384061.aspx).  
  
In einigen Fällen ist es unpraktisch, einen benannten Typ für einfache Sätze verwandter Werte zu erstellen, die nicht außerhalb von Methodengrenzen gespeichert oder übergeben werden sollen. Sie können für diesen Zweck *anonyme Typen* erstellen. Weitere Informationen finden Sie unter [Anonyme Klassentypen](https://msdn.microsoft.com/library/bb397696.aspx).

Es ist üblich, mehr als einen Wert aus einer Methode zurückgeben zu wollen. Sie können *Tupeltypen* erstellen, die mehrere Werte in einem Methodenaufruf zurückgeben. Weitere Informationen finden Sie unter [Tupel](tuples.md)

## <a name="the-common-type-system"></a>Das allgemeine Typsystem  
Sie sollten mit zwei grundlegenden Punkten des Typsystems in .NET Framework vertraut sein:  
  
-   Es unterstützt das Prinzip der Vererbung. Typen können von anderen Typen abgeleitet werden, die als *Basistypen* bezeichnet werden. Der abgeleitete Typ erbt (mit einigen Beschränkungen) die Methoden, Eigenschaften und anderen Member des Basistyps. Der Basistyp kann wiederum von einem anderen Typ abgeleitet sein. In diesem Fall erbt der abgeleitete Typ die Member beider Basistypen in der Vererbungshierarchie. Alle Typen, einschließlich integrierter numerischer Typen, z.B. @System.Int32 (C#-Schlüsselwort: `int`), werden letztendlich von einem einzelnen Basistyp abgeleitet, nämlich @System.Object (C#-Schlüsselwort: `object`). Diese einheitliche Typhierarchie wird als [Allgemeines Typsystem](../standard/common-type-system.md) (Common Type System – CTS) bezeichnet. Weitere Informationen zur Vererbung in C# finden Sie unter [Vererbung](https://msdn.microsoft.com/library/ms173149.aspx).  
  
-   Jeder Typ im CTS ist als *Werttyp* oder *Referenztyp* definiert. Dies betrifft auch alle benutzerdefinierten Typen in der .NET Framework-Klassenbibliothek und Ihre eigenen benutzerdefinierten Typen. Typen, die Sie mithilfe des [struct](https://msdn.microsoft.com/library/ah19swz4.aspx)-Schlüsselworts definieren, sind Werttypen. Alle integrierten numerischen Typen sind **structs**. Weitere Informationen über Werttypen finden Sie unter [Structs](structs.md). Typen, die Sie mithilfe des [class](https://msdn.microsoft.com/library/0b0thckt.aspx)-Schlüsselworts definieren, sind Referenztypen. Weitere Informationen über Referenztypen finden Sie unter [Classes](classes.md). Für Referenztypen und Werttypen gelten unterschiedliche Kompilierzeitregeln und ein anderes Laufzeitverhalten.
 
  
## <a name="see-also"></a>Siehe auch
[Strukturen](structs.md)

[Klassen](classes.md)

