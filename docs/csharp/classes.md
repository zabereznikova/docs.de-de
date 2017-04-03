---
title: Klassen | C#-Handbuch
description: "Erfahren Sie etwas über die Klassentypen und wie Sie diese erstellen"
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
ms.openlocfilehash: 4b5614123d38ae00cb471ef85d0eb92c03c68bba
ms.lasthandoff: 03/13/2017

---

# <a name="classes"></a>Klassen
Eine *Klasse* ist ein Konstrukt, das Ihnen ermöglicht, Ihre eigenen benutzerdefinierten Typen zu erstellen, indem Variablen anderer Typen, Methoden und Ereignisse zusammengefasst werden. Eine Klasse ist mit einem Entwurf vergleichbar. Sie definiert die Daten und das Verhalten eines Typs. Wenn die Klasse nicht als statisch deklariert ist, kann der Clientcode diese durch Erstellen von *Objekten* oder *Instanzen* verwenden, die einer Variable zugeordnet sind. Die Variable verbleibt im Arbeitsspeicher, bis alle Verweise darauf außerhalb des gültigen Bereichs angezeigt werden. Zu diesem Zeitpunkt markiert die CLR sie als geeignet für die Garbage Collection. Wenn die Klasse als [statisch](https://msdn.microsoft.com/library/98f28cdx.aspx) deklariert wird, existiert nur eine Kopie im Arbeitsspeicher, und der Clientcode kann darauf nur über die Klasse selbst zugreifen und nicht über eine *Instanzvariable*. Weitere Informationen finden Sie unter [Statische Klassen und statische Klassenmember](https://msdn.microsoft.com/library/79b3xss3.aspx).  

## <a name="reference-types"></a>Verweistypen  
Ein Typ, der als [Klasse](https://msdn.microsoft.com/library/0b0thckt.aspx) definiert ist, ist ein *Referenztyp*. Wenn Sie zur Laufzeit eine Variable eines Referenztyps deklarieren, enthält die Variable zunächst den Wert [NULL](https://msdn.microsoft.com/library/edakx9da.aspx), bis Sie explizit eine Instanz des Objekts mithilfe des Operators [new](https://msdn.microsoft.com/library/51y09td4.aspx) erstellen oder ihr ein Objekt zuweisen, das an anderer Stelle mithilfe des Operators [new](https://msdn.microsoft.com/library/51y09td4.aspx) erstellt wurde, wie im folgenden Beispiel gezeigt wird:  

[!code-csharp[Verweistypen](../../samples/snippets/csharp/concepts/classes/reference-type.cs)]
  
Beim Erstellen des Objekts wird der Speicher im verwalteten Heap belegt. Die Variable enthält lediglich einen Verweis auf den Speicherort des Objekts. Für Typen im verwalteten Heap ist Mehraufwand erforderlich, wenn sie zugewiesen werden und wenn sie von der automatischen Speicherverwaltungsfunktion der CLR freigegeben werden, was als *Garbage Collection* bezeichnet wird. Die Garbage Collection ist jedoch auch stark optimiert. In den meisten Szenarios führt sie nicht zu einem Leistungsproblem. Weitere Informationen zur Garbage Collection finden Sie unter [Automatische Speicherverwaltung und Garbage Collection](../standard/garbagecollection/gc.md).  
  
Verweistypen unterstützen die *Vererbung* vollständig. Dies ist ein wesentliches Merkmal der objektorientierten Programmierung. Wenn Sie eine Klasse erstellen, können Sie von einer anderen Schnittstelle oder Klasse erben, die nicht als [versiegelt](https://msdn.microsoft.com/library/88c54tsw.aspx) definiert ist. Andere Klassen können von Ihrer Klasse erben und die virtuellen Methoden überschreiben. Weitere Informationen finden Sie unter [Vererbung](https://msdn.microsoft.com/library/ms173149.aspx).

## <a name="declaring-classes"></a>Deklarieren von Klassen  
Klassen werden mithilfe des Schlüsselworts [class](https://msdn.microsoft.com/library/0b0thckt.aspx) deklariert, so wie im folgenden Beispiel dargestellt:  
  
[!code-csharp[Deklarieren von Klassen](../../samples/snippets/csharp/concepts/classes/declaring-classes.cs)]  
  
Dem Schlüsselwort **class** wird der Zugriffsmodifizierer vorangestellt. Da [public](https://msdn.microsoft.com/library/yzh058ae.aspx) in diesem Fall verwendet wird, kann jede Person Objekte aus dieser Klasse erstellen. Der Name der Klasse folgt dem Schlüsselwort **class**. Der Rest der Definition ist der Text einer Klasse, in dem das Verhalten und die Daten definiert sind. Felder, Eigenschaften, Methoden und Ereignisse für eine Klasse werden zusammen als *Klassenmember* bezeichnet.  
  
## <a name="creating-objects"></a>Erstellen von Objekten  
Eine Klasse definiert einen Objekttyp, ist aber selbst kein Objekt. Ein Objekt ist eine konkrete Entität, basierend auf einer Klasse, und wird manchmal als Instanz einer Klasse bezeichnet.  
  
Objekte können mithilfe des Schlüsselworts [new](https://msdn.microsoft.com/library/51y09td4.aspx) erstellt werden, gefolgt vom Namen der Klasse, auf der das Objekt basiert, z.B.:  
  
[!code-csharp[Erstellen von Objekten](../../samples/snippets/csharp/concepts/classes/creating-objects.cs)]   
  
Wenn eine Instanz einer Klasse erstellt wird, wird ein Verweis auf das Objekt zurück an den Programmierer übergeben. Im vorherigen Beispiel ist `object1` ein Verweis auf ein Objekt, das auf `Customer` basiert. Dieser Verweis bezieht sich auf das neue Objekt, enthält jedoch nicht die Objektdaten selbst. In der Tat können Sie einen Objektverweis erstellen, ohne ein Objekt zu erstellen:  
  
[!code-csharp[Erstellen von Objekten](../../samples/snippets/csharp/concepts/classes/creating-objects2.cs)]  
  
Es wird nicht empfohlen, einen Objektverweis wie diesen zu erstellen, der auf kein Objekt verweist. Der Versuch, auf ein Objekt über solch einen Verweis zuzugreifen, schlägt während der Laufzeit fehl. Allerdings kann ein solcher Verweis dazu veranlasst werden, auf ein Objekt zu verweisen, indem entweder ein neues Objekt erstellt wird oder indem es einem vorhandenen Objekt zugewiesen wird, z.B.:  
  
[!code-csharp[Erstellen von Objekten](../../samples/snippets/csharp/concepts/classes/creating-objects3.cs)]  
  
Dieser Code erstellt zwei Objektverweise, die beide auf dasselbe Objekt verweisen. Aus diesem Grund werden alle Änderungen am Objekt, die über `object3` getätigt worden sind, bei nachfolgenden Verwendungen von `object4` berücksichtigt. Da auf Objekte, die auf Klassen basieren, durch Verweise zurückgegriffen wird, sind Klassen als Verweistypen bekannt.  
  
## <a name="class-inheritance"></a>Klassenvererbung  
Die Vererbung erfolgt durch Verwendung einer *Ableitung*, d.h., dass eine Klasse mithilfe einer *Basisklasse* deklariert wird, von der Sie Daten und Verhalten erbt. Eine Basisklasse wird durch Anhängen eines Doppelpunkts sowie des Namens der Basisklasse angegeben, die dem abgeleiteten Klassennamen folgt, z.B.:  
  
[!code-csharp[Vererbung](../../samples/snippets/csharp/concepts/classes/inheritance.cs)]  
  
Wenn eine Klasse eine Basisklasse deklariert, erbt sie alle Member der Basisklasse mit Ausnahme der Konstruktoren.  
  
Anders als in C++ kann eine Klasse in C# nur direkt von einer Basisklasse erben. Da jedoch eine Basisklasse von einer anderen Klasse erben kann, kann eine Klasse indirekt von mehreren Basisklassen erben. Darüber hinaus kann eine Klasse mehr als eine Schnittstelle direkt implementieren. Weitere Informationen finden Sie unter [Schnittstellen](programming-guide/interfaces/index.md).  
  
Eine Klasse kann als [abstrakt](https://msdn.microsoft.com/library/sf985hc5.aspx) deklariert werden. Eine abstrakte Klasse enthält abstrakte Methoden, die über eine Signaturdefinition aber keine Implementierung verfügen. Abstrakte Klassen dürfen nicht instanziiert werden. Sie können nur mithilfe von abgeleiteten Klassen verwendet werden, die die abstrakten Methoden implementieren. Im Gegensatz dazu lässt eine [versiegelte](https://msdn.microsoft.com/library/88c54tsw.aspx) Klasse nicht zu, dass andere Klassen von ihr ableiten. Weitere Informationen finden Sie unter [Abstrakte und versiegelte Klassen und Klassenmember](https://msdn.microsoft.com/library/ms173150.aspx).  
  
Klassendefinitionen können zwischen verschiedenen Quelldateien aufgeteilt werden. Weitere Informationen finden Sie unter [Partielle Klassendefinitionen](https://msdn.microsoft.com/library/wa80x488.aspx).  
  
 
## <a name="example"></a>Beispiel
Im folgenden Beispiel wird eine öffentliche Klasse, die ein einzelnes Feld, eine Methode und eine spezielle Methode namens Konstruktor enthält, definiert. Weitere Informationen finden Sie unter [Konstruktoren](https://msdn.microsoft.com/library/ace5hbzh.aspx). Die Klasse wird dann mit dem Schlüsselwort **new** instanziiert.

[!code-csharp[Klassenbeispiel](../../samples/snippets/csharp/concepts/classes/class-example.cs)]  
  
## <a name="c-language-specification"></a>C#-Sprachspezifikation  
Weitere Informationen finden Sie unter [C#-Sprachspezifikation](https://msdn.microsoft.com/library/ms228593.aspx). Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.
  
## <a name="see-also"></a>Siehe auch  
[C#-Programmierhandbuch](https://msdn.microsoft.com/library/67ef8sbd.aspx)   
[Polymorphismus](https://msdn.microsoft.com/library/ms173152.aspx)   
[Class and struct members (Klassen- und Strukturmember)](https://msdn.microsoft.com/library/ms173113.aspx)   
[Class and struct methods (Klassen- und Strukturmethoden)](https://msdn.microsoft.com/library/ms173114.aspx)   
[Konstruktoren](https://msdn.microsoft.com/library/ace5hbzh.aspx)   
[Destruktoren](https://msdn.microsoft.com/library/66x5fx1b.aspx)   
[Objekte](https://msdn.microsoft.com/library/ms173110.aspx)


