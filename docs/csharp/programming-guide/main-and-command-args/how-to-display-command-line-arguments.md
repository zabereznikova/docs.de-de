---
title: 'Vorgehensweise: Anzeigen von Befehlszeilenargumenten – C#-Programmierleitfaden'
description: Erfahren Sie, wie Sie Befehlszeilenargumente anzeigen. Hier finden Sie ein Codebeispiel und zusätzliche verfügbare Ressourcen.
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
ms.openlocfilehash: 1ac5dc5a5f4e974c9202d2ce23f61071494e1977
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381813"
---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a>Vorgehensweise: Anzeigen von Befehlszeilenargumenten (C#-Programmierleitfaden)
Auf die Argumente, die für eine ausführbare Datei in der Befehlszeile bereitgestellt werden, kann über einen optionalen Parameter für `Main` zugegriffen werden. Die Argumente werden in Form eines Arrays von Zeichenfolgen bereitgestellt. Jedes Element des Arrays enthält ein Argument. Leerzeichen zwischen Argumenten wird entfernt. Beachten Sie z.B. diese Befehlszeilenaufrufe einer fiktiven ausführbaren Datei:  
  
|Eingabe in der Befehlszeile|An Main übergebenes Array von Zeichenfolgen|  
|----------------------------|-------------------------------------|  
|**executable.exe a b c**|"a"<br /><br /> "b"<br /><br /> "c"|  
|**executable.exe one two**|"one"<br /><br /> "two"|  
|**executable.exe "one two" three**|"one two"<br /><br /> "three"|  
  
> [!NOTE]
> Wenn Sie eine Anwendung in Visual Studio ausführen, können Sie Befehlszeilenargumente auf der [Seite „Debuggen“, Projekt-Designer](/visualstudio/ide/reference/debug-page-project-designer) angeben.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel zeigt die Befehlszeilenargumente, die an eine Befehlszeilenanwendung übergeben werden. Die Ausgabe wird für den ersten Eintrag in der obigen Tabelle dargestellt.  
  
 [!code-csharp[csProgGuideMain#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#9)]  
  
## <a name="see-also"></a>Weitere Informationen

- [C#-Programmierhandbuch](../index.md)
- [Erstellen über die Befehlszeile mit csc.exe](../../language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [Main() und Befehlszeilenargumente](./index.md)
- [Main()-Rückgabewerte](./main-return-values.md)
