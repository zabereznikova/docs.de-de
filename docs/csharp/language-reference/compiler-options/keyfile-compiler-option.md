---
title: -keyfile (C#-Compileroptionen) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /keyfile
dev_langs:
- CSharp
helpviewer_keywords:
- /keyfile compiler option [C#]
- -keyfile compiler option [C#]
- keyfile compiler option [C#]
ms.assetid: 0815f9de-ace4-4e98-b4c6-13c55dea40c2
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: 4f9ccbfe7126aac3214ccf08015353eec0490cd4
ms.contentlocale: de-de
ms.lasthandoff: 05/10/2017

---
# <a name="keyfile-c-compiler-options"></a>/keyfile (C#-Compileroptionen)
Gibt den Dateinamen mit dem kryptografischen Schlüssel an.  
  
## <a name="syntax"></a>Syntax  
  
```console  
/keyfile:file  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|----------|----------------|  
|`file`|Der Name der Datei mit dem Schlüssel mit starkem Namen.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn diese Option verwendet wird, fügt der Compiler den öffentlichen Schlüssel von der angegebenen Datei in das Assemblymanifest ein und signiert anschließend die endgültige Assembly mit dem privaten Schlüssel. Geben Sie sn -k `file` in die Befehlszeile ein, um eine Schlüsseldatei zu generieren.  
  
 Wenn Sie mit der Option **/target:module** kompilieren, wird der Name der Schlüsseldatei im Modul aufbewahrt und in die Assembly integriert, die erstellt wird, wenn Sie eine Assembly mit [/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md) kompilieren.  
  
 Außerdem können Sie Ihre Verschlüsselungsinformationen mit [/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md) an den Compiler übergeben. Verwenden Sie [/delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md), wenn die Assembly teilweise signiert werden soll.  
  
 Wenn für die gleiche Kompilierung sowohl /keyfile als auch /keycontainer angegeben werden (über eine Befehlszeilenoption oder ein benutzerdefiniertes Attribut), versucht der Compiler zunächst, den Schlüsselcontainer zu verwenden. Wenn dies erfolgreich ist, wird die Assembly mit den Informationen im Schlüsselcontainer signiert. Wenn den Compiler den Schlüsselcontainer nicht findet, wird versucht, die mit /keyfile angegebene Datei zu verwenden. Wenn dies erfolgreich ist, wird die Assembly mit den Informationen in der Schlüsseldatei signiert, und die Schlüsselinformationen werden im Schlüsselcontainer installiert (vergleichbar mit „sn -i“), sodass der Schlüsselcontainer bei der nächsten Kompilierung gültig ist.  
  
 Beachten Sie, dass die Schlüsseldatei möglicherweise nur den öffentlichen Schlüssel enthält.  
  
 Weitere Informationen finden Sie unter [Erstellen und Verwenden von Assemblys mit starkem Namen](https://msdn.microsoft.com/library/xwb8f617) und [Verzögertes Signieren einer Assembly](../../../framework/app-domains/delay-sign-assembly.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die Seite **Eigenschaften** für das Projekt.  
  
2.  Klicken Sie auf die Eigenschaftenseite **Signieren**.  
  
3.  Modifizieren Sie die Eigenschaft **Schlüsseldatei mit starkem Namen auswählen**.  
  
 Sie können mit <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A> programmgesteuert auf diese Compileroption zugreifen.  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)   
 [NIB: Vorgehensweise: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)
