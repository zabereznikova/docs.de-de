---
title: 'Vorgehensweise: Wiedergabe von Sound in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- playing sounds [Windows Forms], Windows Forms
- sounds [Windows Forms], playing
- sounds
- My.Computer.Audio object [Windows Forms], playing sounds
- examples [Windows Forms], sounds
ms.assetid: 3d3350b7-1ebd-4e05-a738-48ca1160a19d
ms.openlocfilehash: 68a68f05b847877641132e540995f6b14bb6e065
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015802"
---
# <a name="how-to-play-a-sound-from-a-windows-form"></a>Vorgehensweise: Wiedergabe von Sound in Windows Forms
In diesem Beispiel wird zur Laufzeit ein Sound in einem bestimmten Pfad wiedergegeben.

## <a name="example"></a>Beispiel

```vb
Sub PlaySimpleSound()
    My.Computer.Audio.Play("c:\Windows\Media\chimes.wav")
End Sub
```

```csharp
private void playSimpleSound()
{
    SoundPlayer simpleSound = new SoundPlayer(@"c:\Windows\Media\chimes.wav");
    simpleSound.Play();
}
```

## <a name="compiling-the-code"></a>Kompilieren des Codes
 Für dieses Beispiel benötigen Sie Folgendes:

- Ersetzen Sie den Dateinamen `"c:\Windows\Media\chimes.wav"` durch einen gültigen Dateinamen.

- (C#) Ein Verweis auf den <xref:System.Media?displayProperty=nameWithType> -Namespace.

## <a name="robust-programming"></a>Stabile Programmierung
 Dateivorgänge sollten in entsprechende strukturierte Ausnahmebehandlungsblöcke eingeschlossen sein.

 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:

- Der Pfadname ist falsch formatiert. Er enthält beispielsweise unzulässige Zeichen oder besteht nur aus Leerzeichen (<xref:System.ArgumentException>-Klasse).

- Der Pfad ist schreibgeschützt (<xref:System.IO.IOException>-Klasse).

- Der Pfadname ist `null` (<xref:System.ArgumentNullException>-Klasse).

- Der Pfadname ist zu lang (<xref:System.IO.PathTooLongException>-Klasse).

- Der Pfad ist ungültig (<xref:System.IO.DirectoryNotFoundException>-Klasse).

- Der Pfad ist nur ein Doppelpunkt, ":"<xref:System.NotSupportedException> (-Klasse).

## <a name="net-framework-security"></a>.NET Framework-Sicherheit
 Beurteilen Sie den Inhalt der Datei nicht anhand des Dateinamens. Bei der Datei `Form1.vb` handelt es sich zum Beispiel nicht unbedingt um eine Visual Basic-Quelldatei. Überprüfen Sie alle Eingaben, bevor Sie die Daten in der Anwendung verwenden.

## <a name="see-also"></a>Siehe auch

- <xref:System.Media.SoundPlayer>
- [Vorgehensweise: Asynchrones Laden eines Sounds in einem Windows Form](how-to-load-a-sound-asynchronously-within-a-windows-form.md)
