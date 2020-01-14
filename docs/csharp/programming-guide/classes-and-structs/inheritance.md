---
title: Vererbung – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- abstract methods [C#]
- abstract classes [C#]
- inheritance [C#]
- derived classes [C#]
- virtual methods [C#]
- C# language, inheritance
ms.assetid: 81d64ee4-50f9-4d6c-a8dc-257c348d2eea
ms.openlocfilehash: 3c59741fa646111d27f6d1087a9275178c1a41a1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705547"
---
# <a name="inheritance-c-programming-guide"></a>Vererbung (C#-Programmierhandbuch)

Die Vererbung ist, zusammen mit der Kapselung und der Polymorphie, eines der drei primären Charakteristika des objektorientierten Programmierens. Die Vererbung ermöglicht die Erstellung neuer Klassen, die in anderen Klassen definiertes Verhalten wieder verwenden, erweitern und ändern. Die Klasse, deren Member vererbt werden, wird *Basisklasse* genannt, und die Klasse, die diese Member erbt, wird *abgeleitete Klasse* genannt. Eine abgeleitete Klasse kann nur eine direkte Basisklasse haben. Doch die Vererbung ist transitiv. Wenn Klasse C von Klasse B abgeleitet wird, und Klasse B von Klasse A abgeleitet wird, erbt Klasse C die in Klasse B und A deklarierten Member.  
  
> [!NOTE]
> Strukturen unterstützen die Vererbung nicht, aber sie können Schnittstellen implementieren. Weitere Informationen finden Sie unter [Schnittstellen](../interfaces/index.md).  
  
 Konzeptuell gesehen ist die abgeleitete Klasse eine Spezialisierung der Basisklasse. Wenn Sie beispielsweise eine Basisklasse `Animal` haben, haben Sie möglicherweise eine abgeleitete Klasse mit dem Namen `Mammal` und eine andere abgeleitete Klasse mit dem Namen `Reptile`. Ein `Mammal` ist ein `Animal`, und ein `Reptile` ist ein `Animal`, aber jede abgeleitete Klasse repräsentiert unterschiedliche Spezialisierungen der Basisklasse.  
  
 Wenn Sie eine Klasse definieren, die von einer anderen Klasse abgeleitet werden soll, erhält die abgeleitete Klasse implizit alle Member der Basisklasse – ausgenommen davon sind deren Konstruktoren und Finalizern. Die abgeleitete Klasse kann so den Code der Basisklasse wiederverwenden, ohne diesen erneut implementieren zu müssen. Sie können der abgeleiteten Klasse mehr Member hinzufügen. Auf diese Art erweitert die abgeleitete Klasse die Funktionalität der Basisklasse.  
  
 Die folgende Abbildung zeigt eine Klasse `WorkItem`, die ein Arbeitselement in einem Geschäftsprozess repräsentiert. Wie alle Klassen leitet es sich von <xref:System.Object?displayProperty=nameWithType> ab und erbt dessen Methoden. `WorkItem` fügt von allein fünf Member hinzu. Diese beinhalten einen Konstruktor, weil Konstruktoren nicht vererbt werden. Die Klasse `ChangeRequest` erbt von `WorkItem` und repräsentiert eine bestimmt Art von Arbeitselementen. `ChangeRequest` fügt den von `WorkItem` und <xref:System.Object> geerbten Membern zwei weitere Member hinzu. Es muss seinen eigenen Konstruktor hinzufügen, und es fügt auch `originalItemID` hinzu. Die Eigenschaft `originalItemID` ermöglicht es der `ChangeRequest`-Instanz, mit dem ursprünglichen `WorkItem` verknüpft zu werden, für das die Änderungsanforderung gilt.  
  
 ![Diagramm, das die Klassenvererbung zeigt](./media/inheritance/class-inheritance-diagram.png)  
  
 Das folgende Beispiel zeigt, wie die in der oben stehenden Abbildung veranschaulichten Klassenbeziehungen in C# ausgedrückt werden. Das Beispiel zeigt auch, wie `WorkItem` die virtuelle Methode <xref:System.Object.ToString%2A?displayProperty=nameWithType> außer Kraft setzt, und wie die `ChangeRequest`-Klasse die `WorkItem`-Implementierung der Methode erbt.  
  
 [!code-csharp[csProgGuideInheritance#49](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#49)]  
  
## <a name="abstract-and-virtual-methods"></a>Abstrakte und virtuelle Methoden  
 Wenn eine Basisklasse eine Methode als [virtuell](../../language-reference/keywords/virtual.md) deklariert, kann eine abgeleitete Klasse die Methode mit ihrer eigenen Implementierung [außer Kraft setzen](../../language-reference/keywords/override.md). Wenn eine Basisklasse eine Methode als [abstrakt](../../language-reference/keywords/abstract.md) deklariert, muss diese Methode in jeder nicht abstrakten Klasse außer Kraft gesetzt werden, die direkt von dieser Klasse erbt. Wenn eine abgeleitete Klasse selbst abstrakt ist, erbt sie abstrakte Member, ohne diese zu implementieren. Abstrakte und virtuelle Member sind die Basis für Polymorphie, die das zweite charakteristische Merkmal des objektorientierten Programmierens ist. Weitere Informationen finden Sie unter [Polymorphie](./polymorphism.md).  
  
## <a name="abstract-base-classes"></a>Abstrakte Basisklassen  
 Sie können eine Klasse als [abstrakt](../../language-reference/keywords/abstract.md) deklarieren, wenn Sie die direkte Instanziierung mit dem [new](../../language-reference/operators/new-operator.md)-Operator vermeiden möchten. Wenn Sie dies machen, kann die Klasse nur verwendet werden, wenn eine neue Klasse von ihr abgeleitet wird. Eine abstrakte Klasse kann mindestens eine Methodensignatur enthalten, die selbst auch als abstrakt deklariert wurden. Diese Signaturen geben die Parameter und Rückgabewerte an, verfügen aber über keine Implementierung (Methodenkörper). Eine abstrakte Klasse muss nicht zwangsläufig abstrakte Member enthalten; wenn eine Klasse allerdings einen abstrakten Member enthält, muss die Klasse an sich auch als abstrakt deklariert werden. Abgeleitete Klassen, die nicht selbst abstrakt sind, müssen eine Implementierung für jede beliebige abstrakte Methode aus einer abstrakten Basisklasse bereitstellen. Weitere Informationen finden Sie unter [Abstrakte und versiegelte Klassen und Klassenmember](./abstract-and-sealed-classes-and-class-members.md).  
  
## <a name="interfaces"></a>Schnittstellen  
 Eine *Schnittstelle* ist ein Verweistyp, der einer abstrakten Basisklasse leicht ähnelt, die nur aus zwei abstrakten Membern besteht. Wenn eine Klasse eine Schnittstelle implementiert, muss sie eine Implementierung für alle Member der Schnittstelle bereitstellen. Eine Klasse kann mehrere Schnittstellen implementieren, auch wenn sie nur von einer einzelnen direkten Basisklasse ableiten kann.  
  
 Schnittstellen werden verwendet, um bestimmte Funktionen zu definieren, die nicht unbedingt in einer „ist ein“-Beziehung zueinander stehen. Die <xref:System.IEquatable%601?displayProperty=nameWithType> -Schnittstelle kann z.B. von jeder beliebigen Klasse oder Struktur implementiert werden, die es Clientcode ermöglichen muss, ermitteln zu können, ob zwei Objekte des Typs äquivalent sind (allerdings definiert der Typ Äquivalenz). <xref:System.IEquatable%601> impliziert nicht dieselbe Art einer „ist ein“-Beziehung, wie sie zwischen einer Basis- und einer abgeleiteten Klasse besteht (z.B. ist ein `Mammal` ein `Animal`). Weitere Informationen finden Sie unter [Schnittstellen](../interfaces/index.md).  
  
## <a name="preventing-further-derivation"></a>Weitere Ableitung verhindern  
 Eine Klasse kann andere Klassen daran hindern, von ihr oder einem ihrer Member zu erben, indem sie sich selbst oder den Member als [versiegelt](../../language-reference/keywords/sealed.md) deklariert. Weitere Informationen zu abstrakten Klassen finden Sie unter [Abstrakte und versiegelte Klassen und Klassenmember](./abstract-and-sealed-classes-and-class-members.md).  
  
## <a name="derived-class-hiding-of-base-class-members"></a>Das Verbergen von Membern der Basisklasse in einer abgeleiteten Klasse  
 Eine abgeleitete Klasse kann Basisklassenmember verbergen, indem sie Member mit demselben Namen und derselben Signatur deklariert. Der Modifizierer [new](../../language-reference/keywords/new-modifier.md) kann verwendet werden, um explizit anzugeben, dass der Member nicht dazu vorgesehen ist, den Basismember außer Kraft zu setzen. Das Verwenden von [new](../../language-reference/keywords/new-modifier.md) ist nicht erforderlich, aber es wird eine Compilerwarnung generiert, wenn [new](../../language-reference/keywords/new-modifier.md) nicht verwendet wird. Weitere Informationen finden Sie unter [Versionsverwaltung mit den Schlüsselwörtern „override“ und „new“](./versioning-with-the-override-and-new-keywords.md) und [Wann müssen die Schlüsselwörter „override“ und „new“ verwendet werden?](./knowing-when-to-use-override-and-new-keywords.md).  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Klassen und Strukturen](./index.md)
- [class](../../language-reference/keywords/class.md)
- [struct](../../language-reference/keywords/struct.md)
