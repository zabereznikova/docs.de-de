---
title: -nullable (C#-Compileroptionen)
author: IEvangelist
ms.author: dapine
ms.date: 06/04/2020
f1_keywords:
- /nullable
helpviewer_keywords:
- nullable compiler option [C#]
- /nullable compiler option [C#]
- -nullable compiler option [C#]
ms.openlocfilehash: f1aba7e08f472411640d42f51d78ca6f7e5cc900
ms.sourcegitcommit: 4ad2f8920251f3744240c3b42a443ffbe0a46577
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2020
ms.locfileid: "86100885"
---
# <a name="-nullable-c-compiler-options"></a>-nullable (C#-Compileroptionen)

Mit der Option **-nullable** können Sie einen gewünschten Nullable-Kontext festlegen.

## <a name="syntax"></a>Syntax

```console
-nullable[+ | -]
-nullable:{enable | disable | warnings | annotations}
```

## <a name="arguments"></a>Argumente

`+` &#124; `-`  
Wenn `+` oder **-nullable** angegeben wird, erlaubt der Compiler Nullable-Kontexte. Wenn `-` angegeben wird, werden Nullable-Kontexte nicht erlaubt. Dies gilt auch, wenn Sie **-nullable** nicht angeben.

`enable` &#124; `disable` &#124; `warnings` &#124; `annotations`  
Mit diesen Argumenten wird die Option für den Nullable-Kontext angegeben. Diese funktionieren ähnlich wie die Argumente `+` und `-`, die jeweils zum Zulassen und Verweigern dienen, ermöglichen jedoch eine präzisere Kontrolle über den Nullable-Kontext. Das `enable`-Argument, das im Grunde genommen mit der Angabe von **-nullable** übereinstimmt, aktiviert den Nullwerte zulassenden Kontext. Durch Angeben von `disable` werden Nullable-Kontexte nicht zugelassen. Wenn das `warnings`-Argument angegeben wird ( **-nullable:warnings**), werden Nullable-Kontexte zugelassen. Wenn das `annotations`-Argument angegeben wird ( **-nullable:annotations**), werden Nullable-Kontexte zugelassen.

## <a name="remarks"></a>Hinweise

Die Ablaufsteuerungsanalyse wird dazu verwendet, die NULL-Zulässigkeit von Variablen in ausführbarem Code abzuleiten. Die abgeleitete NULL-Zulässigkeit einer Variable ist unabhängig von der deklarierten NULL-Zulässigkeit der Variable. Methodenaufrufe werden auch analysiert, wenn sie bedingt ausgelassen werden. Dies gilt beispielsweise für die Methode <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> im Releasemodus.

Das Aufrufen von Methoden, die mit den folgenden Attributen versehen sind, wirken sich auf die Ablaufsteuerungsanalyse aus:

- Einfache Vorbedingungen: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> und <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute>
- Einfache Nachbedingungen: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> und <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute>
- Bedingte Nachbedingungen: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> und <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute>
- <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute> (z. B. `DoesNotReturnIf(false)` für <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>) und <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute>
- <xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute>
- Nachbedingungen für Member: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> und <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])>

### <a name="to-set-this-compiler-option-in-a-project"></a>Festlegen dieser Compileroption in einem Projekt

Bearbeiten Sie die *CSPROJ*-Datei, um das `<Nullable>`-Tag in einer `Project/PropertyGroup`-Hierarchie hinzuzufügen:

```xml
<Project Sdk="...">

  <PropertyGroup>
    <Nullable>enable</Nullable>
  </PropertyGroup>

</Project>
```

## <a name="see-also"></a>Siehe auch

- [C#-Compileroptionen](./index.md)
- [Nullwerte zulassende Verweistypen](../../nullable-references.md)
