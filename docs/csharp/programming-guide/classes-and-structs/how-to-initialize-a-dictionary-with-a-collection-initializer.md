---
title: 'Gewusst wie: Initialisieren eines Wörterbuchs mit einem Auflistungsinitialisierer (C#-Programmierhandbuch)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- collection initializers [C#], with Dictionary
ms.assetid: 25283922-f8ee-40dc-a639-fac30804ec71
caps.latest.revision: ''
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8b8de5fb85a839d52ad00ad552ef823d9817e9b7
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2018
---
# <a name="how-to-initialize-a-dictionary-with-a-collection-initializer-c-programming-guide"></a>Gewusst wie: Initialisieren eines Wörterbuchs mit einem Auflistungsinitialisierer (C#-Programmierhandbuch)
Eine <xref:System.Collections.Generic.Dictionary`2> enthält eine Sammlung von Schlüssel-Wert-Paaren. Die <xref:System.Collections.Generic.Dictionary`2.Add*>-Methode nimmt zwei Parameter an, einen für den Schlüssel und einen für den Wert. Um eine <xref:System.Collections.Generic.Dictionary`2>-Klasse oder eine beliebige Sammlung zu initialisieren, deren `Add`-Methode mehrere Parameter annimmt, schließen Sie einen Satz von Parametern in Klammern ein, so wie im folgenden Beispiel dargestellt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird <xref:System.Collections.Generic.Dictionary`2> mit Instanzen vom Typ `StudentName` initialisiert.  
  
 [!code-csharp[csProgGuideLINQ#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-a-dictionary-with-a-collection-initializer_1.cs)]  
  
 Beachten Sie die zwei Paare geschweifter Klammern in jedem Element der Auflistung. Die inneren Klammern umschließen den Objektinitialisierer für `StudentName`, und die äußeren Klammern umschließen den Initialisierer für das Schlüssel/Wertpaar, das `students`<xref:System.Collections.Generic.Dictionary`2> hinzugefügt wird. Schließlich wird der ganze Auflistungsinitialisierer für das Wörterbuch in geschweifte Klammern eingeschlossen.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Um diesen Code auszuführen, kopieren Sie die Klasse, und fügen Sie sie in ein Visual C#-Konsolenanwendungsprojekt ein, das in [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)] erstellt wurde. Standardmäßig wird dieses Projekt mit Version 3.5 von [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] verwendet und verfügt über einen Verweis auf „System.Core.dll“ und eine using-Anweisung für „System.Linq“. Wenn eine oder mehrere dieser Anforderungen im Projekt nicht vorhanden sind, können Sie sie manuell hinzufügen.  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Objekt- und Auflistungsinitialisierer](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)
