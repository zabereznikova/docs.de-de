---
title: -refout (C# Compileroptionen)
ms.date: 08/08/2017
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [C#]
- /refout compiler option [C#]
- -refout compiler option [C#]
ms.openlocfilehash: f48316a1e6f657e3bd0190d269dfe0e875a833d9
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771760"
---
# <a name="-refout-c-compiler-options"></a>-refout (C# Compileroptionen)

Die Option **-refout** gibt einen Dateipfad an, an den die Verweisassembly ausgegeben werden soll. Dies entspricht `metadataPeStream` in der Emit-API. Diese Option entspricht der Projekteigenschaft [ProduceReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) von MSBuild.

## <a name="syntax"></a>Syntax

```console
-refout:filepath
```

## <a name="arguments"></a>Argumente

 `filepath`: Der Dateipfad für die Verweisassembly. Dieser sollte im Allgemeinen mit der primären Assembly übereinstimmen. Die empfohlene Konvention (von MSBuild verwendet) ist die, die Verweisassembly in einem „ref/“-Unterordner zu platzieren, der relativ zur primären Assembly ist.

## <a name="remarks"></a>Anmerkungen

Verweisassemblys sind eine besondere Art von Assembly, die nur die Mindestmenge an Metadaten enthalten, die zum Darstellen der öffentlichen API-Oberfläche der Bibliothek erforderlich sind. Sie beinhalten Deklarationen für alle Member, die beim Verweis auf eine Assembly in Buildtools von Bedeutung sind, schließen aber alle Memberimplementierungen und Deklarationen privater Member aus, die keine beobachtbaren Auswirkungen auf ihren API-Vertrag haben. Weitere Informationen finden Sie unter [Verweisassemblys](../../../standard/assembly/reference-assemblies.md) im .NET-Leitfaden.

Die Optionen `-refout` und [`-refonly`](refonly-compiler-option.md) schließen sich gegenseitig aus.

## <a name="see-also"></a>Siehe auch

- [C#-Compileroptionen](./index.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
