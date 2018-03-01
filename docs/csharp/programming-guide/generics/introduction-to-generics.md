---
title: "Einführung in Generika (C#-Programmierhandbuch)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- generics [C#], about generics
ms.assetid: a1ad761e-42f7-41dd-a62f-452a2de26b9d
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 61baf26c9f942a59e3787ca55a2ac6a824410608
ms.sourcegitcommit: 3fd4e718d1bac9769fe0c1dd08ca1b2323ae272b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2018
---
# <a name="introduction-to-generics-c-programming-guide"></a>Einführung in Generika (C#-Programmierhandbuch)
Generische Klassen und Methoden vereinen Wiederverwendbarkeit, Typsicherheit und Effizienz so, wie es ihre nicht generischen Gegenstücke nicht können. Generika werden am häufigsten für Auflistungen und deren Methoden verwendet. Version 2.0 der .NET Framework-Klassenbibliothek bietet einen neuen Namespace, <xref:System.Collections.Generic>, der mehrere neue generikabasierte Auflistungsklassen enthält. Es wird empfohlen, dass alle Anwendungen für [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 2.0 und höher die neue generische Auflistungsklasse statt der älteren nicht generischen Gegenstücke wie etwa <xref:System.Collections.ArrayList> verwenden. Weitere Informationen finden Sie unter [Generika in der .NET Framework-Klassenbibliothek](../../../csharp/programming-guide/generics/generics-in-the-net-framework-class-library.md).  
  
 Sie können selbstverständlich auch benutzerdefinierte generische Typen und Methoden erstellen, um Ihre eigenen typsicheren und effizienten Lösungen und Entwurfsmuster bereitzustellen. Das folgende Codebeispiel zeigt eine einfache generische linked-list-Klasse zur Veranschaulichung. (In den meisten Fällen sollten Sie die Klasse <xref:System.Collections.Generic.List%601> verwenden., die von der .NET Framework-Klassenbibliothek bereitgestellt wird, statt Ihre eigene zu erstellen.) Der Typparameter `T` wird an mehreren Stellen verwendet, wo für gewöhnlich ein konkreter Typ verwendet werden würde, um den Typ des Elements anzugeben, das in der Liste gespeichert wurde. Er wird wie folgt verwendet:  
  
-   Als Typ eines Methodenparameters in der Methode `AddHead`.  
  
-   Als Rückgabetyp der Eigenschaft `Data` in der geschachtelten Klasse `Node`.  
  
-   Als Typ des privaten Members `data` in der geschachtelten Klasse.  
  
 Beachten Sie, dass T für die geschachtelte Klasse `Node` zur Verfügung steht. Wenn `GenericList<T>` mit einem konkreten Typ instanziiert wird, beispielsweise als `GenericList<int>`, wird jedes `T` durch `int` ersetzt.  
  
 [!code-csharp[csProgGuideGenerics#2](../../../csharp/programming-guide/generics/codesnippet/CSharp/introduction-to-generics_1.cs)]  
  
 Das folgende Codebeispiel zeigt, wie Clientcode die generische Klasse `GenericList<T>` verwendet, um eine Ganzzahlliste zu erstellen. Indem Sie einfach das Typargument ändern, kann der folgende Code ganz leicht so modifiziert werden, dass er Zeichenfolgenlisten oder jeden anderen benutzerdefinierten Typ erstellt:  
  
 [!code-csharp[csProgGuideGenerics#3](../../../csharp/programming-guide/generics/codesnippet/CSharp/introduction-to-generics_2.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Collections.Generic>  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Generika](../../../csharp/programming-guide/generics/index.md)
