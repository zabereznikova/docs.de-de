---
description: -filealign (C#-Compileroptionen)
title: -filealign (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /filealign
helpviewer_keywords:
- /alignment compiler option [C#]
- filealign compiler option [C#]
- -filealign compiler option [C#]
- /sections compiler option [C#]
- alignment compiler option [C#]
- sections compiler option [C#]
- -sections compiler option [C#]
- /filealign compiler option [C#]
- file sharing [C#]
- -alignment compiler option [C#]
- section alignment [C#]
ms.assetid: 15cf1c98-3798-4ced-9f08-60619308a073
ms.openlocfilehash: 4b61217a3d6812ea3ab036f82d49bba05c20629e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173242"
---
# <a name="-filealign-c-compiler-options"></a>-filealign (C#-Compileroptionen)

Mit der Option **-filealign** können Sie die Größe der Abschnitte in Ihrer Ausgabedatei angeben.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-filealign:number  
```  
  
## <a name="arguments"></a>Argumente  

 `number`  
 Ein Wert, der die Größe der Abschnitte in der Ausgabedatei angibt. Gültige Werte sind 512, 1024, 2048, 4096 und 8192. Diese Werte sind in Bytes angegeben.  
  
## <a name="remarks"></a>Hinweise  

 Jeder Abschnitt wird auf einer Grenze angeordnet, die ein Vielfaches des Werts **-filealign** darstellt. Es gibt keinen festen Standardwert. Wenn **-filealign** nicht angegeben ist, wählt die Common Language Runtime zur Kompilierzeit einen Standardwert.  
  
 Das Angeben der Abschnittsgröße wirkt sich auf die Größe der Ausgabedatei aus. Das Ändern der Größe kann möglicherweise für Programme hilfreich sein, die auf kleineren Geräten ausgeführt werden.  
  
 Verwenden Sie [DUMPBIN](/cpp/build/reference/dumpbin-options), um Informationen über Abschnitte in Ihrer Ausgabedatei anzuzeigen.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1. Öffnen Sie die Seite **Eigenschaften** des Projekts.  
  
2. Klicken Sie auf die Eigenschaftenseite **Erstellen**.  
  
3. Klicken Sie auf die Schaltfläche **Erweitert** .  
  
4. Ändern der Eigenschaft **Dateianordnung**.  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.FileAlignment%2A>.  
  
## <a name="see-also"></a>Weitere Informationen

- [C#-Compileroptionen](./index.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
