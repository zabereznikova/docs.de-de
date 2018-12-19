---
title: Initialisieren eines Wörterbuchs mit einem Auflistungsinitialisierer – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [C#], with Dictionary
ms.assetid: 25283922-f8ee-40dc-a639-fac30804ec71
ms.openlocfilehash: 42deee85b3a425531ddadfa96cfaff6d342d1221
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243880"
---
# <a name="how-to-initialize-a-dictionary-with-a-collection-initializer-c-programming-guide"></a>Initialisieren eines Wörterbuchs mit einem Auflistungsinitialisierer (C#-Programmierhandbuch)

Eine <xref:System.Collections.Generic.Dictionary%602> enthält eine Sammlung von Schlüssel-Wert-Paaren. Die <xref:System.Collections.Generic.Dictionary%602.Add*>-Methode nimmt zwei Parameter an, einen für den Schlüssel und einen für den Wert. Um eine <xref:System.Collections.Generic.Dictionary%602>-Klasse oder eine beliebige Sammlung zu initialisieren, deren `Add`-Methode mehrere Parameter annimmt, schließen Sie einen Satz von Parametern in Klammern ein, so wie im folgenden Beispiel dargestellt.

## <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird <xref:System.Collections.Generic.Dictionary%602> mit Instanzen vom Typ `StudentName` initialisiert.  
  
[!code-csharp[csProgGuideLINQ#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-a-dictionary-with-a-collection-initializer_1.cs)]

Beachten Sie die zwei Paare geschweifter Klammern in jedem Element der Auflistung. Die inneren Klammern umschließen den Objektinitialisierer für `StudentName`, und die äußeren Klammern umschließen den Initialisierer für das Schlüssel-Wert-Paar, das `students` <xref:System.Collections.Generic.Dictionary%602> hinzugefügt wird. Schließlich wird der ganze Auflistungsinitialisierer für das Wörterbuch in geschweifte Klammern eingeschlossen.

## <a name="compiling-the-code"></a>Kompilieren des Codes

Kopieren Sie die Klasse, und fügen Sie sie in ein Visual C#-Konsolenanwendungsprojekt ein, das in Visual Studio erstellt wurde, um den Code auszuführen. Standardmäßig wird dieses Projekt mit Version 3.5 von [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] verwendet und verfügt über einen Verweis auf „System.Core.dll“ und eine using-Anweisung für „System.Linq“. Wenn eine oder mehrere dieser Anforderungen im Projekt nicht vorhanden sind, können Sie sie manuell hinzufügen.

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
- [Objekt- und Auflistungsinitialisierer](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)
