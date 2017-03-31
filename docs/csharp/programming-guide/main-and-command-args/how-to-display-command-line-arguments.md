---
title: 'Vorgehensweise: Anzeigen von Befehlszeilenargumenten (C#-Programmierhandbuch) | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e46860ecc2f5062abb440a764443ecee19c5153d
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a>Gewusst wie: Anzeigen von Befehlszeilenargumenten (C#-Programmierhandbuch)
Auf die Argumente, die für eine ausführbare Datei in der Befehlszeile bereitgestellt wurden, können Sie über einen optionalen Parameter für `Main` zugreifen. Die Argumente werden in Form eines Arrays von Zeichenfolgen bereitgestellt. Jedes Element des Arrays enthält ein Argument. Leerzeichen zwischen Argumenten wird entfernt. Beachten Sie z.B. diese Befehlszeilenaufrufe einer fiktiven ausführbaren Datei:  
  
|Eingabe in der Befehlszeile|An Main übergebenes Array von Zeichenfolgen|  
|----------------------------|-------------------------------------|  
|**executable.exe a b c**|"a"<br /><br /> "b"<br /><br /> "c"|  
|**executable.exe one two**|"one"<br /><br /> "two"|  
|**executable.exe "one two" three**|"one two"<br /><br /> "three"|  
  
> [!NOTE]
>  Wenn Sie eine Anwendung in Visual Studio ausführen, können Sie Befehlszeilenargumente auf der [Seite „Debuggen“, Projekt-Designer](https://docs.microsoft.com/visualstudio/ide/reference/debug-page-project-designer) angeben.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel werden die Befehlszeilenargumente gezeigt, die an eine Befehlszeilenanwendung übergeben werden. Die Ausgabe wird für den ersten Eintrag in der obigen Tabelle dargestellt.  
  
 [!code-cs[csProgGuideMain#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-display-command-line-arguments_1.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Erstellen über die Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)   
 [Main() und Befehlszeilenargumente](../../../csharp/programming-guide/main-and-command-args/index.md)   
 [Vorgehensweise: Zugreifen auf Befehlszeilenargumente mithilfe von foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)   
 [Main()-Rückgabewerte](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)
