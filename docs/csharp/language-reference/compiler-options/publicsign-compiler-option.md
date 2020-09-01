---
description: -publicsign (C#-Compileroptionen)
title: -publicsign (C#-Compileroptionen)
ms.date: 05/15/2018
f1_keywords:
- /publicsign
helpviewer_keywords:
- -publicsign compiler option [C#]
- publicsign compiler option [C#]
- /publicsign compiler option [C#]
ms.openlocfilehash: 525912c7f50aa6b51e602be7b9258f1f5907daac
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89124811"
---
# <a name="-publicsign-c-compiler-options"></a>-publicsign (C#-Compileroptionen)

Diese Option bewirkt, dass der Compiler einen öffentlichen Schlüssel anwendet, die Assembly aber tatsächlich nicht signiert. Mit der Option **-publicsign** wird zudem ein Bit in der Assembly festgelegt, das der Runtime mitteilt, dass die Datei tatsächlich signiert wurde.

## <a name="syntax"></a>Syntax

```console
-publicsign
```

## <a name="arguments"></a>Argumente

Keine.

## <a name="remarks"></a>Hinweise

Für die Option **-publicsign** müssen die Optionen [-keyfile](keyfile-compiler-option.md) oder [-keycontainer](keycontainer-compiler-option.md) verwendet werden. Die Optionen **keyfile** oder **keycontainer** geben den öffentlichen Schlüssel an.

Die Optionen **-delaysign** und **-publicsign** schließen sich gegenseitig aus.

Bei der öffentlichen Signierung, die manchmal auch als „Fake-Signierung“ oder „OSS-Signierung“ bezeichnet wird, wird der öffentliche Schlüssel in eine Ausgabeassembly eingefügt und das Flag „signed“ (signiert) festgelegt. Die Assembly wird jedoch nicht wirklich mit einem privaten Schlüssel signiert. Dies ist bei Open Source-Projekten hilfreich, bei denen Personen Assemblys erstellen möchten, die mit den veröffentlichten, „vollständig signierten“ Assemblys kompatibel sind, jedoch keinen Zugriff auf den privaten Schlüssel zum Signieren der Assemblys haben. Da fast keine Benutzer tatsächlich überprüfen müssen, ob die Assembly vollständig signiert ist, können diese öffentlich erstellten Assemblys in fast jedem Szenario eingesetzt werden, in denen die vollständig signierte Assembly verwendet werden würde.

### <a name="to-set-this-compiler-option-in-a-csproj-file"></a>Festlegen dieser Compileroption in einer CSPROJ-Datei

Öffnen Sie die CSPROJ-Datei für ein Projekt, und fügen Sie das folgende Element hinzu:

```xml
<PublicSign>true</PublicSign>
```

## <a name="see-also"></a>Weitere Informationen

- [C#-Compileroption „-delaysign“](delaysign-compiler-option.md)
- [C#-Compileroption „-keyfile“](keyfile-compiler-option.md)
- [C#-Compileroption „-keycontainer“](keycontainer-compiler-option.md)
- [C#-Compileroptionen](index.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
