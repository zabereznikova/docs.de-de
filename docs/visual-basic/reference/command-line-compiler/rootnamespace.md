---
title: / RootNamespace | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /rootnamespace
- rootnamespace
dev_langs:
- VB
helpviewer_keywords:
- /rootnamespace compiler option [Visual Basic]
- -rootnamespace compiler option [Visual Basic]
- rootnamespace compiler option [Visual Basic]
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
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
ms.openlocfilehash: 7b261efeb829a6c0b035d7364c63074412a91c7f
ms.lasthandoff: 03/13/2017

---
# <a name="rootnamespace"></a>/rootnamespace
Gibt einen Namespace für alle Typdeklarationen an.  
  
## <a name="syntax"></a>Syntax  
  
```  
/rootnamespace:namespace  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`namespace`|Der Name des Namespaces in das alle Typdeklarationen für das aktuelle Projekt eingeschlossen.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie die ausführbare Datei (Devenv.exe) von Visual Studio erstellten Projekt kompilieren in der Visual Studio IDE, verwenden `/rootnamespace` zum Angeben des Werts, der die <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A>Eigenschaft.</xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> Finden Sie unter [Devenv-Befehlszeilenschalter](https://docs.microsoft.com/visualstudio/ide/reference/devenv-command-line-switches) Weitere Informationen.  
  
 Verwenden Sie die common Language Runtime MSIL-Disassembler (ich`ldasm.exe`) die Namespacenamen in der Ausgabedatei anzeigen.  
  
|Zum Festlegen von/RootNamespace in Visual Studio integrierte Entwicklungsumgebung|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Auf der **Projekt** Menü klicken Sie auf **Eigenschaften**. Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Klicken Sie auf die Registerkarte **Anwendung** .<br />3.  Ändern Sie den Wert in der **Stamm-Namespace** Feld.|  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `In.vb` und alle Typdeklarationen im Namespace `mynamespace`.  
  
```  
vbc /rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Ildasm.exe (IL-Disassembler)](https://msdn.microsoft.com/library/f7dy01k1)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
