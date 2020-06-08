---
title: -delaysign
ms.date: 03/10/2018
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
ms.openlocfilehash: c9bb302e2b34ebe1f51cf39bb3db1094d420d7f4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408698"
---
# <a name="-delaysign"></a>-delaysign

Gibt an, ob die Assembly vollständig oder teilweise signiert wird.

## <a name="syntax"></a>Syntax

```console
-delaysign[+ | -]
```

## <a name="arguments"></a>Argumente

`+` &#124; `-`  
Dies ist optional. Verwenden Sie `-delaysign-`, wenn die Assembly vollständig signiert werden soll. Verwenden Sie `-delaysign+`, wenn Sie den öffentlichen Schlüssel in der Assembly platzieren und Speicherplatz für den signierten Hash reservieren möchten. Der Standardwert ist `-delaysign-`.

## <a name="remarks"></a>Hinweise

Die Option `-delaysign` hat keine Auswirkung, wenn Sie nicht mit [-keyfile](keyfile.md) oder [-keycontainer](keycontainer.md) verwendet wird.

Wenn Sie eine vollständig signierte Assembly anfordern, wird vom Compiler der Hash der Datei mit dem Manifest (Assemblymetadaten) erstellt und mit dem privaten Schlüssel signiert. Die sich ergebende digitale Signatur wird in der Datei mit dem Manifest gespeichert. Wenn eine Assembly mit Verzögerung signiert wird, wird die Signatur vom Compiler nicht berechnet und gespeichert, sondern lediglich ein Bereich in der Datei reserviert, damit die Signatur zu einem späteren Zeitpunkt hinzugefügt werden kann.

Beispielsweise kann ein Entwickler in einer Organisation mithilfe von `-delaysign+` nicht signierte Testversionen einer Assembly verteilen, die Tester mit dem globalen Assemblycache registrieren und verwenden können. Wenn die Arbeit an der Assembly abgeschlossen ist, kann die Person, die für den privaten Schlüssel der Organisation zuständig ist, die Assembly vollständig signieren. Diese Trennung schützt den privaten Schlüssel der Organisation vor der Offenlegung und ermöglicht es allen Entwicklern, an den Assemblys zu arbeiten.

Weitere Informationen zum Signieren von Assemblys finden Sie unter [Erstellen und Verwenden von Assemblys mit starkem Namen](../../../standard/assembly/create-use-strong-named.md).

### <a name="to-set--delaysign-in-the-visual-studio-integrated-development-environment"></a>So legen Sie -delaysign in der Visual Studio-IDE fest

1. Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.

2. Klicken Sie auf die Registerkarte **Signierung**.

3. Legen Sie den Wert im Feld **Nur verzögerte Signierung** fest.

## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](index.md)
- [-keyfile](keyfile.md)
- [-keycontainer](keycontainer.md)
- [Beispiele für Kompilierungsbefehlszeilen](sample-compilation-command-lines.md)
