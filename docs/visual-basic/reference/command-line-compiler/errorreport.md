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
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775670"
---
# <a name="-errorreport"></a>-errorreport

Gibt an, wie der Visual Basic Compiler interne Compilerfehler melden soll.

## <a name="syntax"></a>Syntax

```console
-errorreport:{ prompt | queue | send | none }
```

## <a name="remarks"></a>Hinweise

Diese Option bietet eine bequeme Möglichkeit, dem Visual Basic Team bei Microsoft eine Visual Basic interner Compilerfehler (ICE) zu melden. Standardmäßig sendet der Compiler keine Informationen an Microsoft. Wenn jedoch ein interner Compilerfehler auftritt, können Sie mit dieser Option den Fehler an Microsoft melden. Diese Informationen helfen den Microsoft-Technikern dabei, die Ursache zu identifizieren und die nächste Version von Visual Basic zu verbessern.

Die Fähigkeit eines Benutzers, Berichte zu senden, hängt von den Berechtigungen für Computer-und Benutzerrichtlinien ab.

In der folgenden Tabelle werden die Auswirkungen der Option `-errorreport` zusammengefasst.

|Option|Verhalten|
|---|---|
|`prompt`|Wenn ein interner Compilerfehler auftritt, wird ein Dialogfeld angezeigt, in dem Sie die genauen Daten anzeigen können, die der Compiler gesammelt hat. Sie können feststellen, ob vertrauliche Informationen im Fehlerbericht vorliegen, und entscheiden, ob die Informationen an Microsoft gesendet werden sollen. Wenn Sie sich dafür entscheiden, Sie zu senden, und die Computer-und Benutzerrichtlinien Einstellungen dies zulassen, sendet der Compiler die Daten an Microsoft.|
|`queue`|Der Fehlerbericht wird in die Warteschlange gesetzt. Wenn Sie sich mit Administratorrechten anmelden, können Sie alle Fehler melden, die seit der letzten Anmeldung aufgetreten sind (Sie werden nicht mehr als einmal alle drei Tage aufgefordert, Berichte zu Fehlern zu senden). Dies ist das Standardverhalten, wenn die `-errorreport`-Option nicht angegeben ist.|
|`send`|Wenn ein interner Compilerfehler auftritt und die Computer-und Benutzerrichtlinien Einstellungen dies zulassen, sendet der Compiler die Daten an Microsoft.<br /><br /> Die Option `-errorreport:send` versucht, automatisch Fehlerinformationen an Microsoft zu senden, wenn die Berichterstellung durch die [Windows-Fehlerberichterstattung](/windows/desktop/wer/windows-error-reporting) Systemeinstellungen aktiviert wird. |
|`none`|Wenn ein interner Compilerfehler auftritt, wird er nicht gesammelt oder an Microsoft gesendet.|

Der Compiler sendet Daten, die den Stapel zum Zeitpunkt des Fehlers enthalten, der normalerweise den Quellcode enthält. Wenn `-errorreport` mit der Option [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) verwendet wird, wird die gesamte Quelldatei gesendet.

Diese Option wird am besten mit der Option [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) verwendet, da Microsoft-Technikern den Fehler einfacher reproduzieren können.

> [!NOTE]
> Die `-errorreport`-Option ist in der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.

## <a name="example"></a>Beispiel

Der folgende Code versucht, `T2.vb` zu kompilieren. wenn der Compiler auf einen internen Compilerfehler stößt, werden Sie aufgefordert, den Fehlerbericht an Microsoft zu senden.

```console
vbc -errorreport:prompt t2.vb
```

## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)
