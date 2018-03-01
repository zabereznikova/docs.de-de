---
title: 'Assembly kann nicht ausgegeben: &lt;Fehlermeldung&gt;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b19b6439d85822c69adac0b3e0e04b2f31299836
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="unable-to-emit-assembly-lterror-messagegt"></a>Assembly kann nicht ausgegeben: &lt;Fehlermeldung&gt;
Der [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]-Compiler ruft den Assemblylinker (Al.exe, auch bekannt als Alink) auf, um eine Assembly mit einem Manifest zu erstellen. Dabei meldet der Linker einen Fehler in der Ausgabephase der Assemblyerstellung.  
  
 **Fehler-ID:** BC30145  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Überprüfen Sie die angegebene Fehlermeldung, und wenden Sie sich an das Thema [Al.exe](../../../framework/tools/al-exe-assembly-linker.md). für weitere erläuterungen und Hinweise zu erhalten.  
  
2.  Wiederholen Sie die Assembly manuell zu signieren, entweder die [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) oder [Sn.exe (Strong Name-Tool)](../../../framework/tools/sn-exe-strong-name-tool.md).  
  
3.  Wenn der Fehler weiterhin besteht, tragen Sie Informationen zu den Umständen zusammen, und benachrichtigen Sie den Produktsupport von Microsoft.  
  
### <a name="to-sign-the-assembly-manually"></a>So signieren Sie die Assembly manuell  
  
1.  Verwenden Sie [Sn.exe (Strong Name-Tool)][Sn.exe (Strong Name-Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)) um ein öffentliches/privates Schlüsselpaar-Datei zu erstellen.  
  
     Die Dateierweiterung dieser Datei lautet .snk.  
  
2.  Löschen Sie den COM-Verweis, der für den Fehler verantwortlich ist, aus Ihrem Projekt.  
  
3.  Vom Windows **starten** Sie im Menü **Programme**, zeigen Sie auf **Microsoft Visual Studio 2008**, zeigen Sie auf **Visual Studio-Tools**, und Klicken Sie dann auf **Visual Studio 2008-Eingabeaufforderung**.  
  
4.  Wechseln Sie in das Verzeichnis, in das Sie den Assemblywrapper platzieren möchten.  
  
5.  Geben Sie den folgenden Code ein.  
  
    ```  
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>  
    ```  
  
     Im Folgenden finden Sie ein Beispiel für den von Ihnen eingegebenen Code.  
  
    ```  
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"  
    ```  
  
     Verwenden Sie doppelte Anführungszeichen ("), wenn ein Pfad oder eine Datei Leerzeichen enthält.  
  
6.  Fügen Sie in [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] einen .NET Assembly-Verweis auf die gerade von Ihnen erstellte Datei hinzu.  
  
## <a name="see-also"></a>Siehe auch  
 
 [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).  
 [Sn.exe (Strong Name-Tool)] [Sn.exe (Strong Name-Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))  
 [Vorgehensweise: Erstellen eines öffentlichen/privaten Schlüsselpaars](../../../framework/app-domains/how-to-create-a-public-private-key-pair.md)  
 [Sprechen Sie mit uns](/visualstudio/ide/talk-to-us)
