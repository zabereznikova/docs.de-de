---
title: 'Assembly wurde nicht generiert: &lt;Fehlermeldung&gt; | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30145
- bc30145
dev_langs:
- VB
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
caps.latest.revision: 11
author: stevehoag
ms.author: shoag
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: dac4b133882c043f9c84e936bad2e36f35fc4c33
ms.lasthandoff: 03/13/2017

---
# <a name="unable-to-emit-assembly-lterror-messagegt"></a>Assembly wurde nicht generiert: &lt;Fehlermeldung&gt;
Der [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]-Compiler ruft den Assemblylinker (Al.exe, auch bekannt als Alink) auf, um eine Assembly mit einem Manifest zu erstellen. Dabei meldet der Linker einen Fehler in der Ausgabephase der Assemblyerstellung.  
  
 **Fehler-ID:** BC30145  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Überprüfen Sie die angezeigte Fehlermeldung an, und wenden Sie sich an das Thema [Al.exe Tool Fehler und Warnungen](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) Weitere Hinweise und Tipps.  
  
2.  Wiederholen Sie die Assembly manuell zu signieren, entweder mithilfe der [Al.exe (Assembly Linker)](https://msdn.microsoft.com/library/c405shex) oder [Sn.exe (Strong Name-Tool)](https://msdn.microsoft.com/library/k5b5tt23).  
  
3.  Wenn der Fehler weiterhin besteht, tragen Sie Informationen zu den Umständen zusammen, und benachrichtigen Sie den Produktsupport von Microsoft.  
  
### <a name="to-sign-the-assembly-manually"></a>So signieren Sie die Assembly manuell  
  
1.  Verwenden der [Sn.exe (Strong Name-Tool)](https://msdn.microsoft.com/library/k5b5tt23) zum Erstellen einer Datei Schlüsselpaar aus öffentlichem und privatem Schlüssel.  
  
     Die Dateierweiterung dieser Datei lautet .snk.  
  
2.  Löschen Sie den COM-Verweis, der für den Fehler verantwortlich ist, aus Ihrem Projekt.  
  
3.  Von der Windows **Start** auf **Programme**, zeigen Sie auf **Microsoft Visual Studio 2008**, zeigen Sie auf **Visual Studio-Tools**, und klicken Sie dann auf **Visual Studio 2008 Command Prompt**.  
  
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
  
6.  Fügen Sie in [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] einen .NET Assembly-Verweis auf die gerade von Ihnen erstellte Datei hinzu.  
  
## <a name="see-also"></a>Siehe auch  
 [Al.exe (Assemblylinker)](https://msdn.microsoft.com/library/c405shex)   
 [Al.exe-Tools-Fehler und Warnungen](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b)   
 [Sn.exe (Strong Name-Tool)](https://msdn.microsoft.com/library/k5b5tt23)   
 [Vorgehensweise: Erstellen eines öffentlichen/privaten Schlüsselpaars](http://msdn.microsoft.com/library/05026813-f3bd-4d7c-9e0b-fc588eb3d114)   
 [Sprechen Sie mit uns](https://docs.microsoft.com/visualstudio/ide/talk-to-us)
