---
title: / delaysign | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- /delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 59d4ec227286c20b2b4ecf749a91f0c4ee8d25ca
ms.lasthandoff: 03/13/2017

---
# <a name="delaysign"></a>/delaysign
Gibt an, ob die Assembly vollständig oder teilweise signiert wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
/delaysign[+ | -]  
```  
  
## <a name="arguments"></a>Argumente  
 `+` &#124; `-`  
 Optional. Verwenden Sie `/delaysign-`, wenn die Assembly vollständig signiert werden soll. Verwendung `/delaysign+` Wenn Sie den öffentlichen Schlüssel in der Assembly, und reservieren Speicherplatz für den signierten Hash platzieren möchten. Die Standardeinstellung ist `/delaysign-`.  
  
## <a name="remarks"></a>Hinweise  
 Die `/delaysign` Option hat keine Auswirkung, wenn Sie mit [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) oder [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).  
  
 Wenn Sie eine vollständig signierte Assembly anfordern, wandelt der Compiler die Datei, die das Manifest (Assemblymetadaten) enthält und signiert dieses Hash mit dem privaten Schlüssel. Die sich ergebende digitale Signatur wird in der Datei mit dem Manifest gespeichert. Wenn eine Assembly verzögert signiert wird, wird der Compiler nicht berechnet und die Signatur sondern reserviert Speicherplatz in der Datei speichern, damit die Signatur später hinzugefügt werden kann.  
  
 Zum Beispiel mithilfe von `/delaysign+`, ein Entwickler in einer Organisation kann verteilen, nicht signierte Testversionen einer Assembly, die Tester für den globalen Assemblycache registrieren und verwenden können. Bei der Arbeit an der Assembly abgeschlossen ist, kann die für den privaten Schlüssel der Organisation verantwortliche Person die Assembly vollständig signiert. Diese Trennung verhindert Offenlegung, wobei alle Entwickler auf die Assemblys privaten Schlüssel der Organisation.  
  
 Finden Sie unter [erstellen und Assemblys mit starkem Namen](https://msdn.microsoft.com/library/xwb8f617) für Weitere Informationen zum Signieren einer Assemblys.  
  
### <a name="to-set-delaysign-in-the-visual-studio-integrated-development-environment"></a>Zum Festlegen von/delaysign in Visual Studio integrierte Entwicklungsumgebung  
  
1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Auf der **Projekt** Menü klicken Sie auf **Eigenschaften**. Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Klicken Sie auf die **Signierung** Registerkarte.  
  
3.  Legen Sie den Wert der **nur verzögerte Signierung** Feld.  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/ keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)   
 [/ keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
