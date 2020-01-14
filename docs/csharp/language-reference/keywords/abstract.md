---
title: abstract – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- abstract
- abstract_CSharpKeyword
helpviewer_keywords:
- abstract keyword [C#]
ms.assetid: b0797770-c1f3-4b4d-9441-b9122602a6bb
ms.openlocfilehash: 96e8bbce2e67c316d5cd1cd78e3e2506dabead25
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713862"
---
# <a name="abstract-c-reference"></a>abstract (C#-Referenz)
Der `abstract`-Modifizierer gibt an, dass dem modifizierten Objekt eine Implementierung fehlt oder dass diese unvollständig ist. Der abstract-Modifizierer kann für Klassen, Methoden, Eigenschaften, Indexer und Ereignisse verwendet werden. Verwenden Sie den `abstract`-Modifizierer in einer Klassendeklaration, um anzugeben, dass die Klasse nur die Basisklasse für andere Klassen sein und nicht selbst instanziiert werden soll. Als abstrakt markierte Member müssen von Klassen, die von nicht abstrakten Klassen abgeleitet wurden, implementiert werden.
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel muss die Klasse `Square` eine Implementierung von `GetArea` bereitstellen, da sie von `Shape` abgeleitet ist:  
  
 [!code-csharp[csrefKeywordsModifiers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#1)]
  
 Abstrakte Klassen weisen die folgenden Funktionen auf:  
  
- Eine abstrakte Klasse darf nicht instanziiert werden.  
  
- Eine abstrakte Klasse enthält möglicherweise abstrakte Methode und Accessoren.  
  
- Eine abstrakte Klasse kann nicht mit dem [sealed](./sealed.md)-Modifizierer geändert werden, da sich die beiden Modifizierer gegenseitig ausschließen. Der `sealed`-Modifizierer verhindert das Vererben einer Klasse, und der `abstract`-Modifizierer erfordert das Vererben einer Klasse.  
  
- Eine nicht abstrakte Klasse, die von einer abstrakten Klasse abgeleitet wurde, muss Implementierungen aller geerbten abstrakten Methoden und Accessoren enthalten.  
  
 Verwenden Sie den `abstract`-Modifizierer in einer Methoden- oder Eigenschaftendeklaration, um anzugeben, dass die Methode oder Eigenschaft keine Implementierung enthalten.  
  
 Abstrakte Methoden weisen die folgenden Funktionen auf:  
  
- Eine abstrakte Methode ist implizit eine virtuelle Methode.  
  
- Abstrakte Methodendeklarationen sind nur in abstrakten Klassen zulässig.  
  
- Es gibt keinen Methodenkörper, da eine abstrakte Methodendeklaration keine Implementierungen bietet; die Methodendeklaration enden ganz einfach mit einem Semikolon; auf die Signatur folgen keine geschweiften Klammern ({ }). Zum Beispiel:  
  
    ```csharp  
    public abstract void MyMethod();  
    ```  
  
     Die Implementierung wird von der Methode [override](./override.md) zur Verfügung gestellt, die ein Member einer nicht abstrakten Klasse ist.  
  
- Es ist unzulässig, die Modifizierer [static](./static.md) oder [virtual](./virtual.md) in einer abstrakten Methodendeklaration zu verwenden.  
  
 Abstrakte Eigenschaften verhalten sich wie abstrakte Methoden – sie unterscheiden sich lediglich in der Deklarations- und Aufrufsyntax.  
  
- Es ist ein unzulässig, den `abstract`-Modifizierer für eine statische Eigenschaft zu verwenden.  
  
- Eine abstrakte vererbte Eigenschaft kann in einer abgeleiteten Klasse mithilfe der Eigenschaftendeklaration, die den Modifizierer [override](./override.md) verwendet, außer Kraft gesetzt werden.  
  
 Weitere Informationen über abstrakte Klassen finden Sie unter [Abstrakte und versiegelte Klassen und Klassenmember](../../programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).  
  
 Eine abstrakte Klasse muss eine Implementierung für alle Schnittstellenmember bereitstellen.  
  
 Eine abstrakte Klasse, die eine Schnittstelle implementiert, ordnet die Schnittstellenmethoden möglicherweise abstrakten Methoden zu. Zum Beispiel:  
  
[!code-csharp[csrefKeywordsModifiers#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#2)]
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird die `DerivedClass`-Klasse von der abstrakten Klasse `BaseClass` abgeleitet. Die abstrakte Klasse enthält eine abstrakte Methode, `AbstractMethod`, und zwei abstrakte Eigenschaften, `X` und `Y`.  
  
[!code-csharp[csrefKeywordsModifiers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#3)]
  
 Wenn Sie beim vorherigen Beispiel versuchen, die abstrakte Klasse mithilfe des folgenden Anweisungsbeispiels zu instanziieren:  
  
```csharp
BaseClass bc = new BaseClass();   // Error  
```  
  
Sie erhalten eine Fehlermeldung, dass der Compiler keine Instanz der abstrakten Klasse „BaseClass“ erstellen kann.  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [Modifizierer](index.md)
- [virtual](./virtual.md)
- [override](./override.md)
- [C#-Schlüsselwörter](./index.md)
