---
title: 'Fehler beim Erstellen des Assemblymanifests: &lt;Fehlermeldung&gt; | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30140
- vbc30140
dev_langs:
- VB
helpviewer_keywords:
- BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
caps.latest.revision: 13
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
ms.openlocfilehash: 35a912bbcab78178ce636afa550c244823da512c
ms.lasthandoff: 03/13/2017

---
# <a name="error-creating-assembly-manifest-lterror-messagegt"></a>Fehler beim Erstellen des Assemblymanifests: &lt;Fehlermeldung&gt;
Der [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]-Compiler ruft den Assemblylinker (Al.exe, auch bekannt als Alink) auf, um eine Assembly mit einem Manifest zu erstellen. Der Linker meldet einen Fehler in der Vorausgabestufe der Assemblyerstellung.  
  
 Zu diesem Fehler kann es kommen, wenn es Probleme mit der angegebenen Schlüsseldatei oder dem angegebenen Schlüsselcontainer gibt. Um eine Assembly vollständig zu signieren, müssen Sie eine gültige Schlüsseldatei bereitstellen, die Informationen zu den öffentlichen und privaten Schlüsseln enthält. Um eine Assembly verzögert signieren, wählen Sie die **nur verzögerte Signierung** und geben Sie eine gültige Schlüsseldatei, die Informationen zu den öffentlichen Schlüssel enthält. Der private Schlüssel ist nicht erforderlich, wenn eine Assembly verzögert signiert wird. Weitere Informationen finden Sie unter [Gewusst wie: Signieren einer Assembly (Visual Studio)](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564).  
  
 **Fehler-ID:** BC30140  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Überprüfen Sie die angezeigte Fehlermeldung an, und wenden Sie sich an das Thema [Al.exe Tool Fehler und Warnungen](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) für Fehler al1019, um weitere Erklärung und Hinweise  
  
2.  Wenn der Fehler weiterhin besteht, tragen Sie Informationen zu den Umständen zusammen, und benachrichtigen Sie den Produktsupport von Microsoft.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Signieren einer Assembly (Visual Studio)](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564)   
 [Seite „Signierung“, Projekt-Designer](https://docs.microsoft.com/visualstudio/ide/reference/signing-page-project-designer)   
 [Al.exe (Assemblylinker)](https://msdn.microsoft.com/library/c405shex)   
 [Al.exe-Tools-Fehler und Warnungen](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b)   
 [Sprechen Sie mit uns](https://docs.microsoft.com/visualstudio/ide/talk-to-us)
