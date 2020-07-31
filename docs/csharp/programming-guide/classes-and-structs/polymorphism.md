---
title: Polymorphismus – C#-Programmierhandbuch
description: In diesem Artikel erfahren Sie mehr über Polymorphie, einem wichtigen Konzept für objektorientierte Programmiersprachen wie C#, das die Beziehung zwischen Basis und abgeleiteten Klassen beschreibt.
ms.date: 02/08/2020
helpviewer_keywords:
- C# language, polymorphism
- polymorphism [C#]
ms.assetid: 086af969-29a5-4ce8-a993-0b7d53839dab
ms.openlocfilehash: 59b5f5d2d5a8f274845607aeca370c316670bd68
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925448"
---
# <a name="polymorphism-c-programming-guide"></a>Polymorphismus (C#-Programmierhandbuch)

Polymorphismus wird häufig nach der Kapselung und der Vererbung als die dritte Säule der objektorientierten Programmierung bezeichnet. Es handelt sich dabei um ein griechisches Wort, das "Vielgestaltigkeit" bedeutet und zwei verschiedene Aspekte umfasst:
  
- In Methodenparametern, Auflistungen und Arrays können Objekte einer abgeleiteten Klasse zur Laufzeit als Objekte einer Basisklasse behandelt werden. Wenn diese Polymorphie auftritt, entspricht der deklarierte Typ des Objekts nicht mehr dem Runtimetyp.
- Basisklassen können [virtuelle](../../language-reference/keywords/virtual.md) *Methoden* definieren und implementieren und können von abgeleiteten Klassen [überschrieben](../../language-reference/keywords/override.md) werden, was bedeutet, dass sie ihre eigene Definition und Implementierung bereitstellen. Zur Laufzeit, wenn die Methode von Clientcode aufgerufen wird, sucht die CLR den Laufzeittyp des Objekts und ruft die Überschreibung der virtuellen Methode auf. In Ihrem Quellcode können Sie eine Methode in einer Basisklasse aufrufen und bewirken, dass die Methodenversion der abgeleiteten Klasse ausgeführt wird.

Dank virtueller Methoden können Sie auf einheitliche Weise mit Gruppen verwandter Objekte arbeiten. Nehmen Sie beispielsweise an, Sie haben eine Zeichenanwendung, mit der ein Benutzer verschiedene Arten von Formen auf einer Zeichenoberfläche erstellen kann. Zur Kompilierzeit wissen Sie nicht, welche spezifischen Typen von Formen der Benutzer erstellen wird. Die Anwendung muss jedoch alle verschiedenen Formentypen, die erstellt werden, nachverfolgen und diese als Antwort auf die Mausaktionen des Benutzers aktualisieren. Sie können Polymorphismus verwenden, um dieses Problem mithilfe von zwei einfachen Schritten zu lösen:

1. Erstellen Sie eine Klassenhierarchie, in der jede spezifische Formenklasse von einer gemeinsamen Basisklasse abgeleitet wird.
1. Verwenden Sie eine virtuelle Methode, um die entsprechende Methode in einer abgeleiteten Klasse durch einen einzigen Aufruf der Basisklassenmethode aufzurufen.

Erstellen Sie zuerst eine Basisklasse namens `Shape` und abgeleitete Klassen, wie z. B. `Rectangle`, `Circle` und `Triangle`. Geben Sie der `Shape`-Klasse eine virtuelle Methode namens `Draw`, und überschreiben Sie sie in jeder abgeleiteten Klasse, um die jeweilige Form zu zeichnen, die die Klasse darstellt. Erstellen Sie ein `List<Shape>`-Objekt, und fügen Sie die abgeleiteten Klassen `Circle`, `Triangle` und `Rectangle` hinzu.

[!code-csharp[Polymorphism overview](~/samples/snippets/csharp/objectoriented/Inheritance.cs#PolymorphismOverview)]

Um die Zeichenoberfläche zu aktualisieren, verwenden Sie eine [foreach](../../language-reference/keywords/foreach-in.md)-Schleife, um die Liste zu durchlaufen und die `Draw`-Methode für jedes `Shape`-Objekt in der Liste aufzurufen. Obwohl jedes Objekt in der Liste einen deklarierten `Shape`-Typ aufweist, wird der Runtimetyp (die überschriebene Version der Methode in jeder abgeleiteten Klasse) aufgerufen.

[!code-csharp[Polymorphism overview](~/samples/snippets/csharp/objectoriented/Inheritance.cs#UsePolymorphism)]

In C# ist jeder Typ polymorph, da alle Typen, einschließlich benutzerdefinierten Typen, von <xref:System.Object> erben.  

## <a name="polymorphism-overview"></a>Übersicht über Polymorphie

### <a name="virtual-members"></a>Virtuelle Member

Wenn eine abgeleitete Klasse von einer Basisklasse erbt, erhält sie alle Methoden, Felder, Eigenschaften und Ereignisse der Basisklasse. Der Designer der abgeleiteten Klasse kann verschiedene Optionen für das Verhalten der virtuellen Methoden festlegen:

- Die abgeleitete Klasse kann virtuelle Member in der Basisklasse überschreiben, wodurch ein neues Verhalten definiert wird.
- Die abgeleitete Klasse erbt die nächstgelegene Basisklassenmethode, ohne diese zu überschreiben. Das vorhandene Verhalten wird beibehalten, jedoch können weitere Klassen die Methode überschreiben.
- Die abgeleitete Klasse kann neue nicht virtuelle Implementierungen der Member definieren, die die Basisklassenimplementierungen verbergen.

Eine abgeleitete Klasse kann einen Basisklassenmember nur überschreiben, wenn der Basisklassenmember als [virtuell](../../language-reference/keywords/virtual.md) oder [abstrakt](../../language-reference/keywords/abstract.md) deklariert ist. Der abgeleitete Member muss das [override](../../language-reference/keywords/override.md)-Schlüsselwort verwenden, um explizit anzugeben, dass die Methode an dem virtuellen Aufruf beteiligt sein soll. Der folgende Code veranschaulicht dies:

[!code-csharp[Virtual overview](~/samples/snippets/csharp/objectoriented/Inheritance.cs#VirtualMethods)]

Anders als Methoden, Eigenschaften, Ereignisse und Indexer können Felder nicht virtuell sein. Wenn eine abgeleitete Klasse einen virtuellen Member überschreibt, wird dieser Member auch dann aufgerufen, wenn auf eine Instanz dieser Klasse als Instanz der Basisklasse zugegriffen wird. Der folgende Code veranschaulicht dies:

[!code-csharp[Virtual overview example](~/samples/snippets/csharp/objectoriented/Inheritance.cs#SnippetTestVirtualMethods)]

Mithilfe virtueller Methoden und Eigenschaften können abgeleitete Klassen eine Basisklasse erweitern, ohne die Basisklassenimplementierung einer Methode verwenden zu müssen. Weitere Informationen finden Sie unter [Versionsverwaltung mit den Schlüsselwörtern „override“ und „new“](./versioning-with-the-override-and-new-keywords.md). Eine Schnittstelle bietet eine weitere Möglichkeit zur Definition einer Methode bzw. einer Gruppe von Methoden, deren Implementierung von abgeleiteten Klassen übernommen wird. Weitere Informationen finden Sie unter [Schnittstellen](../interfaces/index.md).

### <a name="hide-base-class-members-with-new-members"></a>Ausblenden von Basisklassenmembern für neue Member

Wenn Sie möchten, dass Ihre abgeleiteten Klassen einen Member mit demselben Namen wie ein Member in einer Basisklasse enthalten, können Sie das Schlüsselwort [new](../../language-reference/keywords/new-modifier.md) verwenden, um den Basisklassenmember auszublenden. Das `new`-Schlüsselwort wird dem Rückgabetyp eines Klassenmembers vorangestellt, der ersetzt wird. Der folgende Code veranschaulicht dies:

[!code-csharp[New method overview example](~/samples/snippets/csharp/objectoriented/Inheritance.cs#NewMethods)]

Auf ausgeblendete Klassenmember kann vom Clientcode immer noch zugegriffen werden, indem die Instanz der abgeleiteten Klasse in eine Instanz der Basisklasse umgewandelt wird. Zum Beispiel:

[!code-csharp[New method overview usage](~/samples/snippets/csharp/objectoriented/Inheritance.cs#UseNewMethods)]

### <a name="prevent-derived-classes-from-overriding-virtual-members"></a>Verhindern der Überschreibung virtueller Member durch abgeleitete Klassen  

Virtuelle Member bleiben virtuell, unabhängig davon, wie viele Klassen zwischen dem virtuellen Member und der Klasse deklariert werden, die ihn ursprünglich deklariert hat. Wenn die Klasse `A` einen virtuellen Member deklariert, die Klasse `B` von `A` abgeleitet und die Klasse `C` von `B` abgeleitet wird, erbt die Klasse `C` den virtuellen Member und kann diesen überschreiben, unabhängig davon, ob die Klasse `B` eine Überschreibung für diesen Member deklariert hat. Der folgende Code veranschaulicht dies:

[!code-csharp[Basic hierarchy](~/samples/snippets/csharp/objectoriented/Hierarchy.cs#FirstHierarchy)]

Eine abgeleitete Klasse kann die virtuelle Vererbung stoppen, indem das Überschreiben als [versiegelt](../../language-reference/keywords/sealed.md) deklariert wird. Zum Beenden der Vererbung muss das Schlüsselwort `sealed` vor dem Schlüsselwort `override` in der Klassenmemberdeklaration eingefügt werden. Der folgende Code veranschaulicht dies:

[!code-csharp[A sealed overridden member](~/samples/snippets/csharp/objectoriented/Hierarchy.cs#SealedOverride)]

Im vorherigen Beispiel ist die Methode `DoWork` für Klassen, die von `C` abgeleitet wurden, nicht mehr virtuell. Für Instanzen von `C` wird sie weiterhin als virtuell betrachtet, auch wenn die Instanzen in den `B`- oder `A`-Typ umgewandelt werden. Versiegelte Methoden können durch abgeleitete Klassen ersetzt werden, indem das Schlüsselwort `new` wie im folgenden Beispiel gezeigt verwendet wird:

[!code-csharp[New method declaration](~/samples/snippets/csharp/objectoriented/Hierarchy.cs#NewDeclaration)]

Wenn `DoWork` für `D` mithilfe einer Variable vom Typ `D` aufgerufen wird, wird in diesem Fall die neue `DoWork`-Methode aufgerufen. Wenn eine Variable vom Typ `C`, `B` oder `A` zum Zugreifen auf eine Instanz von `D` verwendet wird, befolgt ein Aufruf von `DoWork` die Regeln der virtuellen Vererbung, und diese Aufrufe werden an die Implementierung von `DoWork` für die Klasse `C` weitergeleitet.

### <a name="access-base-class-virtual-members-from-derived-classes"></a>Zugreifen auf virtuelle Basisklassenmember über abgeleitete Klassen

Eine abgeleitete Klasse, die eine Methode oder Eigenschaft ersetzt oder überschrieben hat, kann immer noch auf die Methode oder Eigenschaft in der Basisklasse mithilfe des `base`-Schlüsselworts zugreifen. Der folgende Code veranschaulicht dies:

```csharp
public class Base
{
    public virtual void DoWork() {/*...*/ }
}
public class Derived : Base
{
    public override void DoWork()
    {
        //Perform Derived's work here
        //...
        // Call DoWork on base class
        base.DoWork();
    }
}
```

Weitere Informationen finden Sie unter [base](../../language-reference/keywords/base.md).

> [!NOTE]
> Es wird empfohlen, dass virtuelle Member `base` verwenden, um die Basisklassenimplementierung dieses Members in seiner eigenen Implementierung aufzurufen. Durch Zulassen des Basisklassenverhaltens kann sich die abgeleitete Klasse auf die Implementierung von Verhalten konzentrieren, das spezifisch für die abgeleitete Klasse ist. Wenn die Basisklassenimplementierung nicht aufgerufen wird, liegt es an der abgeleiteten Klasse, ihr Verhalten kompatibel mit dem Verhalten der Basisklasse zu gestalten.

## <a name="in-this-section"></a>In diesem Abschnitt

- [Versionsverwaltung mit den Schlüsselwörtern "override" und "new"](./versioning-with-the-override-and-new-keywords.md)
- [Wann müssen die Schlüsselwörter "override" und "new" verwendet werden?](./knowing-when-to-use-override-and-new-keywords.md)
- [Überschreiben der ToString-Methode](./how-to-override-the-tostring-method.md)

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Vererbung](./inheritance.md)
- [Abstrakte und versiegelte Klassen und Klassenmember](./abstract-and-sealed-classes-and-class-members.md)
- [Methoden](./methods.md)
- [Ereignisse](../events/index.md)
- [Eigenschaften](./properties.md)
- [Indexer](../indexers/index.md)
- [Typen](../types/index.md)
