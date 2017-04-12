---
title: / keyfile | Microsoft-Dokumentation
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
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
caps.latest.revision: 17
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
ms.openlocfilehash: c36eac96ac6302db0b567e8249af726c807c2c6c
ms.lasthandoff: 03/13/2017

---
# <a name="keyfile"></a>/keyfile
Gibt eine Datei mit einem Schlüssel oder Schlüsselpaar an, um einer Assembly einen starken Namen zuzuweisen.  
  
## <a name="syntax"></a>Syntax  
  
```  
/keyfile:file  
```  
  
## <a name="arguments"></a>Argumente  
 `file`  
 Erforderlich. Datei, die den Schlüssel enthält. Wenn der Dateiname ein Leerzeichen enthält, schließen Sie den Namen in Anführungszeichen ("").  
  
## <a name="remarks"></a>Hinweise  
 Der Compiler fügt den öffentlichen Schlüssel in das Assemblymanifest ein und signiert anschließend die endgültige Assembly mit dem privaten Schlüssel. Um eine Schlüsseldatei zu generieren, geben Sie `sn -k file` in der Befehlszeile. Weitere Informationen finden Sie unter [Sn.exe (Strong Name-Tool)](https://msdn.microsoft.com/library/k5b5tt23).  
  
 Bei der Kompilierung mit `/target:module`, der Name der Schlüsseldatei im Modul gespeichert und in die Assembly, die erstellt wird, wenn eine Assembly mit aufgenommen [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).  
  
 Sie können auch die Verschlüsselungsinformationen mit an den Compiler übergeben [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md). Verwendung [/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) , wenn Sie eine Assembly teilweise signiert werden soll.  
  
 Sie können diese Option auch als benutzerdefiniertes Attribut angeben (<xref:System.Reflection.AssemblyKeyFileAttribute>) im Quellcode für ein beliebiges Microsoft intermediate Language-Modul.</xref:System.Reflection.AssemblyKeyFileAttribute>  
  
 Sowohl `/keyfile` und [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) sind (entweder durch eine Befehlszeilenoption oder durch ein benutzerdefiniertes Attribut) in der gleichen Kompilierung angegeben, versucht der Compiler zuerst den Schlüsselcontainer. Wenn dies erfolgreich ist, wird die Assembly mit den Informationen im Schlüsselcontainer signiert. Wenn der Compiler den Schlüsselcontainer nicht finden kann, versucht er mit angegebene Datei `/keyfile`. Wenn dies erfolgreich ist, die Assembly mit den Informationen in der Schlüsseldatei signiert wird und die Informationen im Schlüsselcontainer installiert ist (ähnlich wie `sn -i`), damit bei der nächsten Kompilierung die Schlüsselcontainer gültig sein soll.  
  
 Beachten Sie, dass eine Schlüsseldatei möglicherweise nur den öffentlichen Schlüssel enthält.  
  
 Finden Sie unter [erstellen und Assemblys mit starkem Namen](https://msdn.microsoft.com/library/xwb8f617) für Weitere Informationen zum Signieren einer Assemblys.  
  
> [!NOTE]
>  Die `/keyfile` Option ist nicht verfügbar der [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] Entwicklungsumgebung; es ist nur beim Kompilieren von der Befehlszeile aus.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Code wird die Quelldatei `Input.vb` und gibt eine Schlüsseldatei an.  
  
```  
vbc /keyfile:myfile.sn input.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Assemblys und dem globalen Assemblycache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/ Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
