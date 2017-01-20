---
title: "Unable to emit assembly: &lt;error message&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30145"
  - "bc30145"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30145"
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Unable to emit assembly: &lt;error message&gt;
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Der [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Compiler ruft den Assemblylinker \(Al.exe, auch bekannt als Alink\) auf, um eine Assembly mit einem Manifest zu erstellen. Dabei meldet der Linker einen Fehler in der Ausgabephase der Assemblyerstellung.  
  
 **Fehler\-ID:** BC30145  
  
### So beheben Sie diesen Fehler  
  
1.  Überprüfen Sie die angegebene Fehlermeldung, und gehen Sie zum Thema [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/de-de/7f125d49-0a03-47a6-9ba9-d61a679a7d4b), um weitere Erläuterungen und Hinweise zu erhalten.  
  
2.  Versuchen Sie, die Assembly mit dem [Al.exe \(Assembly Linker\-Tool\)](../Topic/Al.exe%20\(Assembly%20Linker\).md) oder dem [Sn.exe \(Strong Name Tool\)](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md) manuell zu signieren.  
  
3.  Wenn der Fehler weiterhin besteht, tragen Sie Informationen zu den Umständen zusammen, und benachrichtigen Sie den Produktsupport von Microsoft.  
  
### So signieren Sie die Assembly manuell  
  
1.  Verwenden Sie das [Sn.exe \(Strong Name Tool\)](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md), um eine Datei mit einem öffentlichen\/privaten Schlüsselpaar zu erstellen.  
  
     Die Dateierweiterung dieser Datei lautet .snk.  
  
2.  Löschen Sie den COM\-Verweis, der für den Fehler verantwortlich ist, aus Ihrem Projekt.  
  
3.  Wählen Sie im Windows\-**Startmenü Programme** und dann **Microsoft Visual Studio 2008**, **Visual Studio\-Tools**, und klicken Sie anschließend auf **Visual Studio 2008\-Eingabeaufforderung**.  
  
4.  Wechseln Sie in das Verzeichnis, in das Sie den Assemblywrapper platzieren möchten.  
  
5.  Geben Sie den folgenden Code ein.  
  
    ```  
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>  
    ```  
  
     Im Folgenden finden Sie ein Beispiel für den von Ihnen eingegebenen Code.  
  
    ```  
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"  
    ```  
  
     Verwenden Sie doppelte Anführungszeichen \("\), wenn ein Pfad oder eine Datei Leerzeichen enthält.  
  
6.  Fügen Sie in [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] einen .NET Assembly\-Verweis auf die gerade von Ihnen erstellte Datei hinzu.  
  
## Siehe auch  
 [Al.exe \(Assembly Linker\-Tool\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)   
 [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/de-de/7f125d49-0a03-47a6-9ba9-d61a679a7d4b)   
 [Sn.exe \(Strong Name Tool\)](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md)   
 [Gewusst wie: Erstellen eines öffentlichen\/privaten Schlüsselpaars](../Topic/How%20to:%20Create%20a%20Public-Private%20Key%20Pair.md)   
 [Sprechen Sie mit uns](/visual-studio/ide/talk-to-us)