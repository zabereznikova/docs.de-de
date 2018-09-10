---
title: 'Gewusst wie: Anzeigen von Befehlszeilenargumenten (C#-Programmierhandbuch)'
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
ms.openlocfilehash: a6067482b4a225abc31592affb2cfab38847cd53
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43502671"
---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a>Gewusst wie: Anzeigen von Befehlszeilenargumenten (C#-Programmierhandbuch)
Auf die Argumente, die für eine ausführbare Datei in der Befehlszeile bereitgestellt wurden, können Sie über einen optionalen Parameter für `Main` zugreifen. Die Argumente werden in Form eines Arrays von Zeichenfolgen bereitgestellt. Jedes Element des Arrays enthält ein Argument. Leerzeichen zwischen Argumenten wird entfernt. Beachten Sie z.B. diese Befehlszeilenaufrufe einer fiktiven ausführbaren Datei:  
  
|Eingabe in der Befehlszeile|An Main übergebenes Array von Zeichenfolgen|  
|----------------------------|-------------------------------------|  
|**executable.exe a b c**|"a"<br /><br /> "b"<br /><br /> "c"|  
|**executable.exe one two**|"one"<br /><br /> "two"|  
|**executable.exe "one two" three**|"one two"<br /><br /> "three"|  
  
> [!NOTE]
>  Wenn Sie eine Anwendung in Visual Studio ausführen, können Sie Befehlszeilenargumente auf der [Seite „Debuggen“, Projekt-Designer](/visualstudio/ide/reference/debug-page-project-designer) angeben.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel werden die Befehlszeilenargumente gezeigt, die an eine Befehlszeilenanwendung übergeben werden. Die Ausgabe wird für den ersten Eintrag in der obigen Tabelle dargestellt.  
  
 [!code-csharp[csProgGuideMain#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-display-command-line-arguments_1.cs)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [Erstellen über die Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)  
- [Main() und Befehlszeilenargumente](../../../csharp/programming-guide/main-and-command-args/index.md)  
- [Gewusst wie: Zugreifen auf Befehlszeilenargumente mithilfe von foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)  
- [Main()-Rückgabewerte](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)
