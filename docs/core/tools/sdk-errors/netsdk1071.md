---
title: 'NETSDK1071: In einem PackageReference-Verweis auf „{0}“ wurde eine Version von `{1}` angegeben.'
description: Hier erfahren Sie, wie Sie das Problem eines PackageReference-Verweises auf ein Metapaket lösen, das im Framework mit einer Version eingeschlossen ist.
author: Forgind
ms.topic: error-reference
ms.date: 10/09/2020
f1_keywords:
- NETSDK1071
ms.openlocfilehash: 852232cba04bb93a17872280e10848c2896991ae
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94445678"
---
# <a name="netsdk1071-explicitly-versioned-packagereference-to-a-metapackage-that-would-be-included-with-the-framework"></a>NETSDK1071: Explizit versionierte PackageReference-Verweise auf ein Metapaket würden in das Framework eingeschlossen werden

**Dieser Artikel gilt für:** ✔️ .NET 5.0.100 SDK und höhere Versionen

Wenn das .NET SDK die Warnung NETSDK1071 ausgibt, deutet dies darauf hin, dass es in der Zukunft möglicherweise einen Versionskonflikt zwischen der Version des Metapakets, wie es in einem PackageReference-Verweis angegeben ist, und der Version des Metapakets, wie auf es implizit über eine TargetFramework-Eigenschaft verwiesen wird, geben könnte:

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp3.1</TargetFramework>
</PropertyGroup>
```

Da TargetFramework automatisch eine Version des Metapakets einführt, kommt es zu einem Konflikt zwischen den Versionen, sollten sich diese jemals unterscheiden.

Problembehebung:

1. Wenn Sie .NET Core oder .NET Standard als Ziel verwenden, sollten Sie dies berücksichtigen und explizite Verweise auf `Microsoft.NETCore.App` oder `NETStandard.Library` in Ihrer Projektdatei vermeiden.
2. Wenn Sie .NET Core als Ziel verwenden und eine bestimmte Version der Runtime benötigen, sollten Sie die `<RuntimeFrameworkVersion>`-Eigenschaft verwenden, anstatt direkt auf Metapakete zu verweisen. Dies kann beispielsweise vorkommen, wenn Sie [eigenständige Bereitstellungen](../../deploying/index.md#publish-self-contained) verwenden und eine bestimmte Patchversion der 1.0.0 LTS-Runtime benötigen.
3. Wenn Sie .NET Standard als Ziel verwenden und eine bestimmte Version von `NetStandard.Library` benötigen, können Sie die `<NetStandardImplicitPackageVersion>`-Eigenschaft verwenden und die Version festlegen, die Sie benötigen.
4. Fügen Sie `Microsoft.NETCore.App` oder `NETSTandard.Library` in .NET Framework-Projekten nicht explizit Verweise hinzu, und aktualisieren Sie diese auch nicht. Wenn bei der Verwendung eines auf .NET Standard basierenden NuGet-Pakets eine bestimmte Version von `NETStandard.Library` benötigt wird, installiert NuGet diese automatisch.
5. Geben Sie keine Version für `Microsoft.AspNetCore.App` oder `Microsoft.AspNetCore.All` an, wenn Sie .NET Core 2.1 oder höher verwenden, da das .NET Core SDK die benötigte Version automatisch auswählt. (Hinweis: Wenn .NET Core 2.1 als Ziel verwendet wird, funktioniert dies nur, wenn das Projekt auch `Microsoft.NET.Sdk.Web` verwendet. Dieses Problem wurde im .NET Core 2.2 SDK gelöst.)
6. Wenn die Warnung nicht mehr angezeigt werden soll, können Sie sie deaktivieren:

   ```xml
   <PackageReference Include="Microsoft.NetCore.App" Version="2.2.8" >
     <AllowExplicitVersion>true</AllowExplicitVersion>
   </PackageReference>
   ```
