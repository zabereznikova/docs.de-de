---
title: /keyfile
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e0be7d230f16750395aaceb3c94539546716b8fd
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="keyfile"></a>/keyfile
Gibt eine Datei mit einem Schlüssel oder Schlüsselpaar an, um einer Assembly einen starken Namen zuzuweisen.  
  
## <a name="syntax"></a>Syntax  
  
```  
/keyfile:file  
```  
  
## <a name="arguments"></a>Argumente  
 `file`  
 Erforderlich. Datei, die den Schlüssel enthält. Wenn der Dateiname ein Leerzeichen enthält, setzen Sie den Namen in Anführungszeichen ("").  
  
## <a name="remarks"></a>Hinweise  
 Der Compiler fügt den öffentlichen Schlüssel in das Assemblymanifest ein und signiert anschließend die endgültige Assembly mit dem privaten Schlüssel. Um eine Schlüsseldatei zu generieren, geben Sie `sn -k file` in der Befehlszeile. Weitere Informationen finden Sie unter [Sn.exe (Strong Name-Tool)][Sn.exe (Strong Name-Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).  
  
 Beim Kompilieren mit `/target:module`, der Namen der Datei mit dem Schlüssel ist im Modul gespeichert und in die Assembly, die erstellt wird, wenn Sie eine Assembly mit Kompilieren integriert [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).  
  
 Außerdem können Sie Ihre Verschlüsselungsinformationen mit [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) an den Compiler übergeben. Verwenden Sie [/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md), wenn die Assembly teilweise signiert werden soll.  
  
 Sie können diese Option auch als benutzerdefiniertes Attribut angeben (<xref:System.Reflection.AssemblyKeyFileAttribute>) im Quellcode für ein beliebiges Modul von Microsoft intermediate Language.  
  
 Sowohl `/keyfile` und [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) sind angegeben (entweder durch eine Befehlszeilenoption oder durch ein benutzerdefiniertes Attribut) in der gleichen Kompilierung, versucht der Compiler zunächst den Schlüsselcontainer. Wenn dies erfolgreich ist, wird die Assembly mit den Informationen im Schlüsselcontainer signiert. Wenn der Compiler den Schlüsselcontainer nicht finden kann, versucht es mit angegebene Datei `/keyfile`. Wenn dies erfolgreich ist, die Assembly mit den Informationen in der Schlüsseldatei signiert wird und die Schlüsselinformationen im Schlüsselcontainer installiert wird (ähnlich wie `sn -i`), damit bei der nächsten Kompilierung die Schlüsselcontainer gültig sein soll.  
  
 Beachten Sie, dass die Schlüsseldatei möglicherweise nur den öffentlichen Schlüssel enthält.  
  
 Finden Sie unter [erstellen und Verwenden von Assemblys](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) für Weitere Informationen zum Signieren einer Assemblys.  
  
> [!NOTE]
>  Die `/keyfile` Option ist nicht verfügbar in der [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] Entwicklungsumgebung; ist verfügbar, nur, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code kompiliert die Quelldatei `Input.vb` und gibt eine Schlüsseldatei an.  
  
```  
vbc /keyfile:myfile.sn input.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Assemblys und der globale Assemblycache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/ Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
