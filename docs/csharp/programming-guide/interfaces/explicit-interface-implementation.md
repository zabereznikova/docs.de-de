---
title: Explizite Schnittstellenimplementierung – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
ms.openlocfilehash: e985da878ca4160938f29911d4313ee6cd731aeb
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244829"
---
# <a name="explicit-interface-implementation-c-programming-guide"></a>Explizite Schnittstellenimplementierung (C#-Programmierhandbuch)
Wenn eine [Klasse](../../../csharp/language-reference/keywords/class.md) zwei Schnittstellen implementiert, die einen Member mit derselben Signatur enthalten, bewirkt die Implementierung dieses Members in der Klasse, dass beide Schnittstellen diesen Member als ihre Implementierung verwenden. Im folgenden Beispiel rufen alle Aufrufe von `Paint` dieselbe Methode auf.  
  
 [!code-csharp[csProgGuideInheritance#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_1.cs)]  
  
 Falls die beiden [Schnittstellen](../../../csharp/language-reference/keywords/interface.md)-Member jedoch nicht dieselbe Funktion erfüllen, kann dies zu einer falschen Implementierung von einer oder beiden Schnittstellen führen. Es ist möglich, einen Schnittstellenmember explizit zu implementieren, also einen Klassenmember zu erstellen, der nur über die Schnittstelle aufgerufen wird und für diese Schnittstelle spezifisch ist. Dazu benennt man den Klassenmember mit dem Namen der Schnittstelle und einem Punkt. Beispiel:  
  
 [!code-csharp[csProgGuideInheritance#40](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_2.cs)]  
  
 Der Klassenmember `IControl.Paint` ist nur über die Schnittstelle `IControl` verfügbar, und `ISurface.Paint` ist nur über `ISurface` verfügbar. Beide Methodenimplementierungen sind getrennt, und keine ist direkt in der Klasse verfügbar. Beispiel:  
  
 [!code-csharp[csProgGuideInheritance#41](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_3.cs)]  
  
 Explizite Implementierung wird auch zum Lösen von Konflikten verwendet, bei denen zwei Schnittstellen verschiedene Member mit demselben Namen deklarieren, z.B. eine Eigenschaft und eine Methode:  
  
 [!code-csharp[csProgGuideInheritance#42](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_4.cs)]  
  
 Um beide Schnittstellen zu implementieren, muss eine Klasse zur Vermeidung eines Compilerfehlers die explizite Implementierung entweder für Eigenschaft P, für Methode P oder für beide verwenden. Zum Beispiel:  
  
 [!code-csharp[csProgGuideInheritance#43](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_5.cs)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md)  
- [Schnittstellen](../../../csharp/programming-guide/interfaces/index.md)  
- [Vererbung](../../../csharp/programming-guide/classes-and-structs/inheritance.md)
