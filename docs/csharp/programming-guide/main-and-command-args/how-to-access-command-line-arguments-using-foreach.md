---
title: 'Gewusst wie: Zugreifen auf Befehlszeilenargumente mithilfe von foreach (C#-Programmierhandbuch)'
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#]
ms.assetid: 89c3e335-3f5b-4e24-8c5a-b8036561fe8a
ms.openlocfilehash: 811ee09aec7afac70f3f2c2fe5fb002232935028
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43511335"
---
# <a name="how-to-access-command-line-arguments-using-foreach-c-programming-guide"></a>Gewusst wie: Zugreifen auf Befehlszeilenargumente mithilfe von foreach (C#-Programmierhandbuch)
Ein weiteres Verfahren zum Durchlaufen von Arrays wird im nachfolgenden Beispiel veranschaulicht: die Verwendung der [foreach](../../../csharp/language-reference/keywords/foreach-in.md)-Anweisung. Die `foreach`-Anweisung kann verwendet werden, um ein Array, eine .NET Framework-Auflistungsklasse oder eine beliebige Klasse bzw. Struktur zu durchlaufen, die die <xref:System.Collections.IEnumerable>-Schnittstelle implementiert.  
  
> [!NOTE]
>  Wenn Sie eine Anwendung in Visual Studio ausführen, können Sie Befehlszeilenargumente auf der [Seite „Debuggen“, Projekt-Designer](/visualstudio/ide/reference/debug-page-project-designer) angeben.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird die Ausgabe der Befehlszeilenargumente mithilfe von `foreach` verdeutlicht.  
  
 [!code-csharp[csProgGuideMain#10](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_1.cs)]  
  
 [!code-csharp[csProgGuideMain#11](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_2.cs)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Array>  
- <xref:System.Collections>  
- [Erstellen über die Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [foreach, in](../../../csharp/language-reference/keywords/foreach-in.md)  
- [Main() und Befehlszeilenargumente](../../../csharp/programming-guide/main-and-command-args/index.md)  
- [Gewusst wie: Anzeigen von Befehlszeilenargumenten](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)  
- [Main()-Rückgabewerte](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)
