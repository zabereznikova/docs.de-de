---
title: / keycontainer | Microsoft-Dokumentation
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
- -keycontainer compiler option [Visual Basic]
- keycontainer compiler option [Visual Basic]
- /keycontainer compiler option [Visual Basic]
ms.assetid: 6a9bc861-1752-4db1-9f64-b5252f0482cc
caps.latest.revision: 16
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
ms.openlocfilehash: 68fa09edce5c0c9af143197f9379d5a46afab52e
ms.lasthandoff: 03/13/2017

---
# <a name="keycontainer"></a>/keycontainer
Gibt einen Schlüsselcontainernamen für ein Schlüsselpaar an, um einer Assembly einen starken Namen zuzuweisen.  
  
## <a name="syntax"></a>Syntax  
  
```  
/keycontainer:container  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`container`|Erforderlich. Containerdatei, die den Schlüssel enthält. Schließen Sie den Dateinamen in Anführungszeichen (""), wenn der Name ein Leerzeichen enthält.|  
  
## <a name="remarks"></a>Hinweise  
 Der Compiler erstellt die teilbar Komponente, indem ein öffentlicher Schlüssel in das Assemblymanifest eingefügt und die endgültige Assembly mit dem privaten Schlüssel signiert. Um eine Schlüsseldatei zu generieren, geben Sie `sn -k``file` in der Befehlszeile. Die `-i` Option installiert das Schlüsselpaar in einem Container. Weitere Informationen finden Sie unter [Sn.exe (Strong Name-Tool)](https://msdn.microsoft.com/library/k5b5tt23).  
  
 Bei der Kompilierung mit `/target:module`, der Name der Schlüsseldatei im Modul gespeichert und in die Assembly, die erstellt wird, wenn eine Assembly mit aufgenommen [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).  
  
 Sie können diese Option auch als benutzerdefiniertes Attribut angeben (<xref:System.Reflection.AssemblyKeyNameAttribute>) im Quellcode für ein beliebiges Microsoft intermediate Language (MSIL)-Modul.</xref:System.Reflection.AssemblyKeyNameAttribute>  
  
 Sie können auch die Verschlüsselungsinformationen mit an den Compiler übergeben [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md). Verwendung [/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) , wenn Sie eine Assembly teilweise signiert werden soll.  
  
 Finden Sie unter [erstellen und Assemblys mit starkem Namen](https://msdn.microsoft.com/library/xwb8f617) für Weitere Informationen zum Signieren einer Assemblys.  
  
> [!NOTE]
>  Die `/keycontainer` Option ist nicht verfügbar in der Visual Studio Development Environment; es ist nur beim Kompilieren von der Befehlszeile aus.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Code wird die Quelldatei `Input.vb` und gibt einen Schlüsselcontainer.  
  
```  
vbc /keycontainer:key1 input.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Assemblys und dem globalen Assemblycache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/ keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
