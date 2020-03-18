---
title: -unsafe (C#-Compileroptionen)
ms.date: 04/25/2018
f1_keywords:
- /unsafe
helpviewer_keywords:
- -unsafe compiler option [C#]
- unsafe compiler option [C#]
- /unsafe compiler option [C#]
ms.openlocfilehash: 146299fda103567b111c66400c17edf36addd843
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "65877995"
---
# <a name="-unsafe-c-compiler-options"></a>-unsafe (C#-Compileroptionen)

Die Compileroption **-unsafe** ermöglicht das Kompilieren von Code, der das [unsafe](../keywords/unsafe.md)-Schlüsselwort verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-unsafe  
```  
  
## <a name="remarks"></a>Hinweise

Weitere Informationen zu unsicherem Code finden Sie unter [Unsicherer Code und Zeiger](../../programming-guide/unsafe-code-pointers/index.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1. Öffnen Sie die Seite **Eigenschaften** des Projekts.  
  
2. Klicken Sie auf die Eigenschaftenseite **Build** .  
  
3. Wählen Sie die **Unsicheren Code zulassen**-Kontrollkästchen.  
  
### <a name="to-add-this-option-in-a-csproj-file"></a>So fügen Sie diese Option in eine CSPROJ-Datei hinzu

Öffnen Sie die CSPROJ-Datei für ein Projekt, und fügen Sie die folgenden Elemente hinzu:

```xml
  <PropertyGroup>
    <AllowUnsafeBlocks>true</AllowUnsafeBlocks>
  </PropertyGroup>
```

 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.  
  
## <a name="example"></a>Beispiel

Kompilieren Sie `in.cs` für den unsicheren Modus:  
  
```console  
csc -unsafe in.cs  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [C#-Compileroptionen](index.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
