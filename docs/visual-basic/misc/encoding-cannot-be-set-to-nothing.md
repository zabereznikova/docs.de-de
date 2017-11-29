---
title: Die Codierung kann nicht auf 'Nothing' festgelegt werden
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: 59f7c731-8291-4a85-bf51-c225e48cdc84
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: daa3567e47f170c64b45cbb9e49d7fa0026b8903
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="encoding-cannot-be-set-to-nothing"></a>Die Codierung kann nicht auf 'Nothing' festgelegt werden
Fehler bei einem Lese- oder Schreibversuch aus einer bzw. in eine Datei, da der Parameter `encoding` auf `Nothing` festgelegt wurde; es ist jedoch ein gültiger Wert erforderlich.  
  
 <xref:System.Text.Encoding> wird verwendet, um zu bestimmen, welche Codierung beim Schreiben in eine Datei verwendet werden soll. Der Standardwert ist UTF-8.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Geben Sie einen gültigen Wert für den `encoding` -Parameter an.  
  
## <a name="see-also"></a>Siehe auch  
 [Dateicodierungen](../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md)  
 [Lesen aus Dateien](../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)  
 [Schreiben in Dateien](../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)  
 [My.Computer.FileSystem.ReadAllText-Methode](http://msdn.microsoft.com/en-us/3a7ac8be-fb1d-4087-bc65-167d6754d57f)  
 [My.Computer.FileSystem.WriteAllText-Methode](http://msdn.microsoft.com/en-us/f507460c-87d9-4504-b74f-3ff825c7d5c4)
