---
title: 'Gewusst wie: Implementieren und Aufrufen einer benutzerdefinierten Erweiterungsmethode – C#-Programmierhandbuch'
description: Informationen zum Implementieren von Erweiterungsmethoden für einen .NET-Typ Clientcode kann Ihre Methoden verwenden, indem ein Verweis auf eine DLL und eine using-Anweisung hinzugefügt werden.
ms.date: 07/20/2015
helpviewer_keywords:
- extension methods [C#], implementing and calling
ms.topic: how-to
ms.custom: contperfq2
ms.assetid: 7dab2a56-cf8e-4a47-a444-fe610a02772a
ms.openlocfilehash: d344489e88ddc2c8cac51afeb5bbc76bc7b42913
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099073"
---
# <a name="how-to-implement-and-call-a-custom-extension-method-c-programming-guide"></a>Gewusst wie: Implementieren und Aufrufen einer benutzerdefinierten Erweiterungsmethode (C#-Programmierhandbuch)

In diesem Artikel wird das Implementieren Ihrer eigenen Erweiterungsmethoden für jeden .NET-Typ behandelt. Der Clientcode kann Ihre Erweiterungsmethoden verwenden, wenn ein Verweis auf die DLL, die die Methoden enthält, und eine [using](../../language-reference/keywords/using-directive.md)-Direktive hinzugefügt werden, die den Namespace angibt, in dem die Erweiterungsmethoden definiert sind.  
  
## <a name="to-define-and-call-the-extension-method"></a>So definieren Sie die Erweiterungsmethode und rufen Sie auf  
  
1. Definieren Sie eine statische [Klasse](./static-classes-and-static-class-members.md), die die Erweiterungsmethode enthalten soll.  
  
     Die Klasse muss für den Clientcode sichtbar sein. Weitere Informationen finden Sie unter [Zugriffsmodifizierer](./access-modifiers.md).  
  
2. Implementieren Sie die Erweiterungsmethode als statische Methode mit mindestens die gleichen Sichtbarkeit wie die enthaltende Klasse.  
  
3. Der erste Parameter der Methode gibt den Typ an, auf den die Methode angewendet wird. Ihm muss ein [this](../../language-reference/keywords/this.md)-Modifizierer vorangehen.  
  
4. Fügen Sie im aufrufenden Code eine `using`-Direktive hinzu, um den [Namespace](../../language-reference/keywords/namespace.md) anzugeben, der die Erweiterungsklassemethode enthält.  
  
5. Rufen Sie die Methoden auf, als wären sie Instanzmethoden für den Typ.  
  
     Beachten Sie, dass der erste Parameter nicht durch einen Aufruf von Code angegeben wird, da er den Typ darstellt, auf den der Operator angewendet wird, und der Compiler bereits den Typ des Objekts kennt. Sie müssen nur Argumente für Parameter 2 bis `n` bereitstellen.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird eine Erweiterungsmethode namens `WordCount` in der `CustomExtensions.StringExtension`-Klasse implementiert. Die Methode wird auf die <xref:System.String>-Klasse angewendet, die als erster Methodenparameter angegeben wird. Der `CustomExtensions`-Namespace wird in den Anwendungsnamespace importiert, und die Methode wird in der `Main`-Methode aufgerufen.  
  
 [!code-csharp[csProgGuideExtensionMethods#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#1)]  
  
## <a name="net-security"></a>.NET-Sicherheit  

 Erweiterungsmethoden enthalten keine speziellen Sicherheitslücken. Sie können nicht dazu verwendet werden, die Identität vorhandener Methoden für einen Typ anzunehmen, da alle Namenskonflikte zugunsten der Instanz oder eine statische Methode gelöst werden, die der Typ selbst definiert. Erweiterungsmethoden können in der erweiterten Klasse nicht auf private Daten zugreifen.  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Erweiterungsmethoden](./extension-methods.md)
- [LINQ (Language Integrated Query)](../../linq/linq-in-csharp.md)
- [Statische Klassen und statische Klassenmember](./static-classes-and-static-class-members.md)
- [protected](../../language-reference/keywords/protected.md)
- [internal](../../language-reference/keywords/internal.md)
- [public](../../language-reference/keywords/public.md)
- [this](../../language-reference/keywords/this.md)
- [namespace](../../language-reference/keywords/namespace.md)
