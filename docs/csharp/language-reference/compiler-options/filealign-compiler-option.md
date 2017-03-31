---
title: -filealign (C#-Compileroptionen) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /filealign
dev_langs:
- CSharp
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
caps.latest.revision: 14
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 83569fa264ba3ed6e271281885940a70a5354840
ms.lasthandoff: 03/13/2017

---
# <a name="filealign-c-compiler-options"></a>/filealign (C#-Compileroptionen)
Mit der Option **/filealign** können Sie die Größe der Abschnitte in Ihrer Ausgabedatei angeben.  
  
## <a name="syntax"></a>Syntax  
  
```  
/filealign:number  
```  
  
## <a name="arguments"></a>Argumente  
 `number`  
 Ein Wert, der die Größe der Abschnitte in der Ausgabedatei angibt. Gültige Werte sind 512, 1024, 2048, 4096 und 8192. Diese Werte sind in Bytes angegeben.  
  
## <a name="remarks"></a>Hinweise  
 Jeder Abschnitt wird auf einer Grenze angeordnet, die ein Mehrfaches des **/filealign**-Werts ist. Es gibt keinen festen Standardwert. Wenn **/filealign** nicht angegeben ist, wird die Common Language Runtime einen Standardwert zur Kompilierzeit wählen.  
  
 Das Angeben der Abschnittsgröße wirkt sich auf die Größe der Ausgabedatei aus. Das Ändern der Größe kann möglicherweise für Programme hilfreich sein, die auf kleineren Geräten ausgeführt werden.  
  
 Verwenden Sie [DUMPBIN](https://docs.microsoft.com/cpp/build/reference/dumpbin-options), um Informationen über Abschnitte in Ihrer Ausgabedatei anzuzeigen.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die **Eigenschaften**-Seite des Projekts.  
  
2.  Klicken Sie auf die Eigenschaftenseite **Build** .  
  
3.  Klicken Sie auf die Schaltfläche **Erweitert** .  
  
4.  Ändern der Eigenschaft **Dateianordnung**.  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.FileAlignment%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)   
 [NIB: Vorgehensweise: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)
