---
title: -keycontainer
ms.date: 03/10/2018
helpviewer_keywords:
- -keycontainer compiler option [Visual Basic]
- keycontainer compiler option [Visual Basic]
- /keycontainer compiler option [Visual Basic]
ms.assetid: 6a9bc861-1752-4db1-9f64-b5252f0482cc
ms.openlocfilehash: 1666c7743f1116f86bc4457af53711cb6f1a6b7b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54579822"
---
# <a name="-keycontainer"></a>-keycontainer
Gibt einen Schlüsselcontainernamen für ein Schlüsselpaar an, um einer Assembly einen starken Namen zuzuweisen.  
  
## <a name="syntax"></a>Syntax  
  
```  
-keycontainer:container  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`container`|Erforderlich. Containerdatei, die den Schlüssel enthält. Schließen Sie den Dateinamen in Anführungszeichen (""), wenn der Name ein Leerzeichen enthält.|  
  
## <a name="remarks"></a>Hinweise  
 Der Compiler erstellt die teilbare Komponente, indem er einen öffentlichen Schlüssel in das Assemblymanifest einfügt und die endgültige Assembly mit dem privaten Schlüssel signiert. Geben Sie `sn -k file` in die Befehlszeile ein, um eine Schlüsseldatei zu generieren. Die `-i` Option installiert das Schlüsselpaar in einem Container. Weitere Informationen finden Sie unter [Sn.exe (Strong Name Tool)][Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).  
  
 Bei der Kompilierung mit `-target:module`, der Name der Schlüsseldatei im Modul aufbewahrt und in die Assembly, die erstellt wird, wenn Sie eine Assembly mit integriert [- Addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).  
  
 Sie können diese Option auch als benutzerdefiniertes Attribut (<xref:System.Reflection.AssemblyKeyNameAttribute>) im Quellcode für ein beliebiges MSIL-Modul (Microsoft Intermediate Language) angeben.  
  
 Außerdem können Sie Ihre Verschlüsselungsinformationen mit [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) an den Compiler übergeben. Verwenden Sie [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md), wenn die Assembly teilweise signiert werden soll.  
  
 Finden Sie unter [erstellen und Assemblys mit starkem Namen](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) für Weitere Informationen zum Signieren einer Assemblys.  
  
> [!NOTE]
>  Die `-keycontainer` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar, sondern nur, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code kompiliert die Quelldatei `Input.vb` und gibt einen Schlüsselcontainer an.  
  
```  
vbc -keycontainer:key1 input.vb  
```  
  
## <a name="see-also"></a>Siehe auch
- [Assemblys und der globale Assemblycache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)
- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
