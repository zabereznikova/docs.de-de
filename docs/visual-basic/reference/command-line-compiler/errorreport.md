---
title: -errorreport
ms.date: 08/14/2018
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
ms.openlocfilehash: a9741f7a8283f8603e02dae5abea151c6ee5d75e
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775670"
---
# <a name="-errorreport"></a>-errorreport

Gibt an, wie interne Compilerfehler vom Visual Basic-Compiler gemeldet werden sollen.

## <a name="syntax"></a>Syntax

```console
-errorreport:{ prompt | queue | send | none }
```

## <a name="remarks"></a>Hinweise

Mit dieser Option können Sie dem Visual Basic-Team von Microsoft auf einfache Weise einen internen Visual Basic-Compilerfehler (ICE) melden. Standardmäßig sendet der Compiler keine Informationen an Microsoft. Tritt jedoch ein interner Compilerfehler auf, können Sie mit dieser Option den Fehler an Microsoft melden. Diese Informationen helfen Microsoft-Entwicklern bei der Ursachensuche und können dazu beitragen, das nächste Visual Basic-Release zu verbessern.

Ob ein Benutzer Berichte senden kann, hängt vom Computer und den Berechtigungen der Benutzerrichtlinien ab.

In der folgenden Tabelle werden die Auswirkungen der Option `-errorreport` zusammengefasst:

|Option|Verhalten|
|---|---|
|`prompt`|Bei Auftreten eines internen Compilerfehlers wird ein Dialogfeld mit den genauen Daten angezeigt, die der Compiler gesammelt hat. Sie entscheiden, ob der Fehlerbericht vertrauliche Informationen enthält und die Informationen an Microsoft gesendet werden sollen. Wenn Sie sich dafür entscheiden, und die Einstellungen des Computers und der Benutzerrichtlinien dies zulassen, sendet der Compiler die Daten an Microsoft.|
|`queue`|Der Fehlerbericht wird in die Warteschlange gesetzt. Wenn Sie sich mit Administratorrechten anmelden, können Sie alle Fehler melden, die seit Ihrer letzten Anmeldung aufgetreten sind (Sie werden nur etwa alle drei Tage zum Senden von Fehlerberichten aufgefordert). Dies ist das Standardverhalten, wenn die Option `-errorreport` nicht angegeben ist.|
|`send`|Bei einem internen Compilerfehler sendet der Compiler die Daten an Microsoft, wenn die Einstellungen des Computers und der Benutzerrichtlinien dies zulassen.<br /><br /> Ist die Berichterstattung in den Systemeinstellungen der [Windows-Fehlerberichterstattung](/windows/desktop/wer/windows-error-reporting) aktiviert, versucht die Option `-errorreport:send`, automatisch Fehlerinformationen an Microsoft zu senden. |
|`none`|Interne Compilerfehler werden weder gesammelt noch an Microsoft gesendet.|

Der Compiler sendet Daten, die den Stapel zum Zeitpunkt des Fehlers und normalerweise auch Quellcode enthalten. Wenn Sie `-errorreport` zusammen mit der Option [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) verwenden, wird die gesamte Quelldatei gesendet.

Verwenden Sie die Option am besten zusammen mit der Option [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md), da auf diese Weise Microsoft-Entwickler den Fehler leichter reproduzieren können.

> [!NOTE]
> Die Option `-errorreport` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.

## <a name="example"></a>Beispiel

Mit dem folgenden Code soll `T2.vb` kompiliert werden. Tritt ein interner Compilerfehler auf, werden Sie vom Compiler dazu aufgefordert, den Fehlerbericht an Microsoft zu senden.

```console
vbc -errorreport:prompt t2.vb
```

## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)
