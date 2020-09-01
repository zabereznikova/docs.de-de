---
description: -refout (C# Compileroptionen)
title: -refout (C# Compileroptionen)
ms.date: 08/08/2017
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [C#]
- /refout compiler option [C#]
- -refout compiler option [C#]
ms.openlocfilehash: 424782e4607fea63130e95ab09a671c75fe1404d
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128713"
---
# <a name="-refout-c-compiler-options"></a>-refout (C# Compileroptionen)

Die Option **-refout** gibt einen Dateipfad an, an den die Verweisassembly ausgegeben werden soll. Dies entspricht `metadataPeStream` in der Emit-API. Diese Option entspricht der Projekteigenschaft [ProduceReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) von MSBuild.

## <a name="syntax"></a>Syntax

```console
-refout:filepath
```

## <a name="arguments"></a>Argumente

 `filepath`: Der Dateipfad für die Verweisassembly. Dieser sollte im Allgemeinen mit der primären Assembly übereinstimmen. Die empfohlene Konvention (von MSBuild verwendet) ist die, die Verweisassembly in einem „ref/“-Unterordner zu platzieren, der relativ zur primären Assembly ist.

## <a name="remarks"></a>Bemerkungen

Verweisassemblys sind eine besondere Art von Assembly, die nur die Mindestmenge an Metadaten enthalten, die zum Darstellen der öffentlichen API-Oberfläche der Bibliothek erforderlich sind. Sie beinhalten Deklarationen für alle Member, die beim Verweis auf eine Assembly in Buildtools von Bedeutung sind, schließen aber alle Memberimplementierungen und Deklarationen privater Member aus, die keine beobachtbaren Auswirkungen auf ihren API-Vertrag haben. Weitere Informationen finden Sie unter [Verweisassemblys](../../../standard/assembly/reference-assemblies.md) im .NET-Leitfaden.

Die Optionen `-refout` und [`-refonly`](refonly-compiler-option.md) schließen sich gegenseitig aus.

## <a name="see-also"></a>Siehe auch

- [C#-Compileroptionen](./index.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
