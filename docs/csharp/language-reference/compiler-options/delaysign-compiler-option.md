---
title: -delaysign (C#-Compileroptionen)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /delaysign
helpviewer_keywords:
- -delaysign compiler option [C#]
- delaysign compiler option [C#]
- /delaysign compiler option [C#]
ms.assetid: bcb058eb-2933-4e7f-b356-5c941db4de75
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 62f76747a29a90562706dff5fa742316c5b99b74
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="delaysign-c-compiler-options"></a>/delaysign (C#-Compileroptionen)
Durch diese Option reserviert der Compiler Speicherplatz in der Ausgabedatei, damit digitale Signaturen später hinzugefügt werden können.  
  
## <a name="syntax"></a>Syntax  
  
```console  
/delaysign[ + | - ]  
```  
  
## <a name="arguments"></a>Argumente  
 `+` &#124; `-`  
 Verwenden Sie **/delaysign-**, wenn die Assembly vollständig signiert werden soll. Verwenden Sie **/delaysign+**, wenn Sie nur den öffentlichen Schlüssel in der Assembly platzieren möchten. Der Standardwert ist **/delaysign-**.  
  
## <a name="remarks"></a>Hinweise  
 Die Option **/delaysign** hat keine Auswirkung, wenn Sie nicht mit [/keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md) oder [/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md) verwendet wird.  
  
 Wenn Sie eine vollständig signierte Assembly anfordern, wird vom Compiler der Hash der Datei mit dem Manifest (Assemblymetadaten) erstellt und mit dem privaten Schlüssel signiert. Die sich ergebende digitale Signatur wird in der Datei mit dem Manifest gespeichert. Wenn eine Assembly mit Verzögerung signiert wird, wird die Signatur vom Compiler nicht berechnet und gespeichert, sondern lediglich ein Bereich in der Datei reserviert, damit die Signatur zu einem späteren Zeitpunkt hinzugefügt werden kann.  
  
 Mit **/delaysign+** können Tester die Assembly beispielsweise im globalen Cache ablegen. Nach dem Testen können Sie die Assembly vollständig signieren, indem Sie den privaten Schlüssel der Assembly mithilfe des Hilfsprogramms [Assembly Linker](../../../framework/tools/al-exe-assembly-linker.md) platzieren.  
  
 Weitere Informationen finden Sie unter [Erstellen und Verwenden von Assemblys mit starkem Namen](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) und [Verzögertes Signieren einer Assembly](../../../framework/app-domains/delay-sign-assembly.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die Seite **Eigenschaften** für das Projekt.  
  
2.  Bearbeiten Sie die Eigenschaft **Nur verzögerte Signierung**.  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)  
 [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
