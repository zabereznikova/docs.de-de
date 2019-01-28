---
title: -unsafe (C#-Compileroptionen)
ms.date: 04/25/2018
f1_keywords:
- /unsafe
helpviewer_keywords:
- -unsafe compiler option [C#]
- unsafe compiler option [C#]
- /unsafe compiler option [C#]
ms.openlocfilehash: 4a8f7d099b2cd3c1b4331c87f853b617fef505ae
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54726532"
---
# <a name="-unsafe-c-compiler-options"></a>-unsafe (C#-Compileroptionen)
Die Compileroption **-unsafe** ermöglicht das Kompilieren von Code, der das [unsafe](../../../csharp/language-reference/keywords/unsafe.md)-Schlüsselwort verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-unsafe  
```  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen zu unsicherem Code finden Sie unter [Unsicherer Code und Zeiger](../../../csharp/programming-guide/unsafe-code-pointers/index.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die Seite **Eigenschaften** des Projekts.  
  
2.  Klicken Sie auf die Eigenschaftenseite **Build** .  
  
3.  Wählen Sie die **Unsicheren Code zulassen**-Kontrollkästchen.  
  
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
  
## <a name="see-also"></a>Siehe auch

- [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
