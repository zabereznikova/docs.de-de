---
title: -keyfile (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /keyfile
helpviewer_keywords:
- /keyfile compiler option [C#]
- -keyfile compiler option [C#]
- keyfile compiler option [C#]
ms.assetid: 0815f9de-ace4-4e98-b4c6-13c55dea40c2
ms.openlocfilehash: 5e5ef095fbb982b0d37d7f44d4d57f27c20a72c1
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43400082"
---
# <a name="-keyfile-c-compiler-options"></a>-keyfile (C#-Compileroptionen)
Gibt den Dateinamen mit dem kryptografischen Schlüssel an.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-keyfile:file  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|----------|----------------|  
|`file`|Der Name der Datei mit dem Schlüssel mit starkem Namen.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn diese Option verwendet wird, fügt der Compiler den öffentlichen Schlüssel von der angegebenen Datei in das Assemblymanifest ein und signiert anschließend die endgültige Assembly mit dem privaten Schlüssel. Geben Sie sn -k `file` in die Befehlszeile ein, um eine Schlüsseldatei zu generieren.  
  
 Wenn Sie mit der Option **-target:module** kompilieren, wird der Name der Schlüsseldatei im Modul aufbewahrt und in die Assembly integriert, die erstellt wird, wenn Sie eine Assembly mit [-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md) kompilieren.  
  
 Außerdem können Sie Ihre Verschlüsselungsinformationen mit [-keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md) an den Compiler übergeben. Verwenden Sie [-delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md), wenn die Assembly teilweise signiert werden soll.  
  
 Wenn für die gleiche Kompilierung sowohl „-keyfile“ als auch „-keycontainer“ angegeben werden (über eine Befehlszeilenoption oder ein benutzerdefiniertes Attribut), versucht der Compiler zunächst, den Schlüsselcontainer zu verwenden. Wenn dies erfolgreich ist, wird die Assembly mit den Informationen im Schlüsselcontainer signiert. Wenn den Compiler den Schlüsselcontainer nicht findet, wird versucht, die mit „-keyfile“ angegebene Datei zu verwenden. Wenn dies erfolgreich ist, wird die Assembly mit den Informationen in der Schlüsseldatei signiert, und die Schlüsselinformationen werden im Schlüsselcontainer installiert (vergleichbar mit „sn -i“), sodass der Schlüsselcontainer bei der nächsten Kompilierung gültig ist.  
  
 Beachten Sie, dass die Schlüsseldatei möglicherweise nur den öffentlichen Schlüssel enthält.  
  
 Weitere Informationen finden Sie unter [Erstellen und Verwenden von Assemblys mit starkem Namen](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) und [Verzögertes Signieren einer Assembly](../../../framework/app-domains/delay-sign-assembly.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die Seite **Eigenschaften** für das Projekt.  
  
2.  Klicken Sie auf die Eigenschaftenseite **Signieren**.  
  
3.  Modifizieren Sie die Eigenschaft **Schlüsseldatei mit starkem Namen auswählen**.  
  
 Sie können mit <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A> programmgesteuert auf diese Compileroption zugreifen.  
  
## <a name="see-also"></a>Siehe auch

- [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)  
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
