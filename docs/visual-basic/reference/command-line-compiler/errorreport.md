---
title: -errorreport
ms.date: 08/14/2018
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d093b8ce4413a375e79eec239be37e83ac674d05
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43509672"
---
# <a name="-errorreport"></a>-errorreport

Gibt an, wie interne Compilerfehler von der Visual Basic-Compiler gemeldet werden sollen.

## <a name="syntax"></a>Syntax

```
-errorreport:{ prompt | queue | send | none }
```

## <a name="remarks"></a>Hinweise

Diese Option bietet eine komfortable Möglichkeit, einen interner Compilerfehler (ICE) von Visual Basic, Visual Basic-Team bei Microsoft. Standardmäßig sendet der Compiler keine Informationen an Microsoft. Allerdings kann diese Option Wenn einen interner Compilerfehler auftritt, Sie den Fehler an Microsoft senden. Diese Informationen helfen Microsoft-Techniker, die die Ursache zu identifizieren und die nächste Version von Visual Basic zu verbessern.

Die Fähigkeit eines Benutzers zum Senden von Berichten hängt von Berechtigungen für Richtlinien für Computer und Benutzer.

Der folgenden Tabelle werden die Auswirkungen der `-errorreport` Option.

|Option|Verhalten|
|---|---|
|`prompt`|Wenn ein interner Compilerfehler auftritt, wird ein Dialogfeld erscheint, so dass Sie die genauen Daten anzeigen können, die der Compiler erfasst. Sie können ermitteln, ob keine vertraulichen Informationen in den Fehlerbericht und treffen einer Entscheidung, ob sie sich an Microsoft senden. Wenn Sie sie senden möchten, und die Richtlinieneinstellungen für Computer- und zulassen, sendet der Compiler die Daten an Microsoft.|
|`queue`|Der Fehlerbericht wird in die Warteschlange gesetzt. Wenn Sie sich mit Administratorberechtigungen anmelden, können Sie Fehler melden, seit dem letzten mit dem Sie angemeldet wurden (Sie werden nicht aufgefordert, Fehlerberichte mehr als einmal alle drei Tage zu senden). Dies ist das Standardverhalten bei der `-errorreport` Option nicht angegeben.|
|`send`|Wenn ein interner Compilerfehler auftritt, und die Richtlinieneinstellungen für Computer- und zulassen, sendet der Compiler die Daten an Microsoft.<br /><br /> Die Option `-errorreport:send` versucht, automatisch die Fehlerinformationen an Microsoft senden, wenn berichterstellung, indem aktiviert ist die [Windows-Fehlerberichterstattung](/windows/desktop/wer/windows-error-reporting) Systemeinstellungen. |
|`none`|Wenn ein interner Compilerfehler auftritt, wird es nicht gesammelt oder an Microsoft gesendet.|

Der Compiler sendet die Daten, die in der Regel einige Quellcode enthält zum Zeitpunkt des Fehlers, der den Stapel enthält. Wenn `-errorreport` wird zusammen mit den [- Bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, und klicken Sie dann die gesamte Quelldatei gesendet wird.

Diese Option wird am besten verwendet, mit der [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, da Microsoft-Techniker so leicht den Fehler reproduzieren können.

> [!NOTE]
> Die `-errorreport` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar, sondern nur, wenn Sie über die Befehlszeile kompilieren.

## <a name="example"></a>Beispiel

Der folgende Code versucht, kompilieren Sie `T2.vb`, und wenn der Compiler einen interner Compilerfehler auftritt, sie werden aufgefordert, den Fehlerbericht an Microsoft zu senden.

```
vbc -errorreport:prompt t2.vb
```

## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)
