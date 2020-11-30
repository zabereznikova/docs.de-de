---
description: -nostdlib (C#-Compileroptionen)
title: -nostdlib (C#-Compileroptionen)
ms.date: 12/20/2019
f1_keywords:
- /nostdlib
helpviewer_keywords:
- nostdlib compiler option [C#]
- -nostdlib compiler option [C#]
- /nostdlib compiler option [C#]
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
ms.openlocfilehash: 214918b32f1f1276eb936e66daba3d372a1e9228
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "89125097"
---
# <a name="-nostdlib-c-compiler-options"></a>-nostdlib (C#-Compileroptionen)

**-nostdlib** verhindert den Import der Datei „mscorlib.dll“, die den gesamten Systemnamespace definiert.

## <a name="syntax"></a>Syntax

```console
-nostdlib[+ | -]
```

## <a name="remarks"></a>Bemerkungen

Verwenden Sie diese Option, wenn Sie Ihren eigenen Systemnamespace und die entsprechenden Objekte definieren oder erstellen möchten.

Wenn Sie **-nostdlib** nicht angeben, wird „mscorlib.dll“ in das Programm importiert (entspricht der Angabe von **-nostdlib-**). Die Angabe von **-nostdlib** entspricht der Angabe von **-nostdlib+** .

### <a name="to-set-this-compiler-option-in-visual-studio"></a>So legen Sie diese Compileroption in Visual Studio fest

> [!NOTE]
> Die folgenden Anweisungen gelten nur für Visual Studio 2015 (und frühere Versionen). Die Buildeigenschaft **Nicht auf mscorlib.dll verweisen** ist in den neueren Versionen von Visual Studio nicht mehr vorhanden.

1. Öffnen Sie die Seite **Eigenschaften** für das Projekt.

2. Klicken Sie auf die Eigenschaftenseite **Erstellen** .

3. Klicken Sie auf die Schaltfläche **Erweitert** .

4. Ändern Sie die Eigenschaft **Nicht auf mscorlib.dll verweisen** .

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.

## <a name="see-also"></a>Weitere Informationen

- [C#-Compileroptionen](./index.md)
