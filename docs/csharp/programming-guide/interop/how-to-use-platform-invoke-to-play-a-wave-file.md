---
title: 'Vorgehensweise: Verwenden eines Plattformaufrufs zum Wiedergeben einer WAV-Datei (C#-Programmierleitfaden)'
description: Dieses C#-Codebeispiel veranschaulicht die Verwendung von Plattformaufrufdiensten zum Wiedergeben einer WAV-Audiodatei unter dem Betriebssystem Windows.
ms.date: 07/20/2015
helpviewer_keywords:
- platform invoke, sound files
- interoperability [C#], playing WAV files using pinvoke
- wav files
- .wav files
ms.assetid: f7f62f53-e026-4c40-b221-3a26adb0c2c5
ms.openlocfilehash: b30cb08e2dcde0eb85e8d88a690ae24bf7ae7f22
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302983"
---
# <a name="how-to-use-platform-invoke-to-play-a-wav-file-c-programming-guide"></a>Vorgehensweise: Verwenden eines Plattformaufrufs zum Wiedergeben einer WAV-Datei (C#-Programmierleitfaden)

Im folgenden C#-Codebeispiel wird die Verwendung von Plattformaufrufdiensten zum Wiedergeben einer WAV-Audiodatei unter dem Betriebssystem Windows veranschaulicht.

## <a name="example"></a>Beispiel

In diesem Beispielcode wird <xref:System.Runtime.InteropServices.DllImportAttribute> verwendet, um den Einstiegspunkt der `PlaySound`-Methode von `winmm.dll` als `Form1 PlaySound()` zu importieren. Das Beispiel hat ein einfaches Windows-Formular mit einer Schaltfläche. Wenn Sie auf die Schaltfläche klicken, öffnet sich das Windows-Standarddialogfeld <xref:System.Windows.Forms.OpenFileDialog>, von wo aus Sie eine Datei zur Wiedergabe öffnen können. Wenn Sie eine Wavedatei auswählen, wird diese mit der `PlaySound()`-Methode der *wimm.dll*-Bibliothek wiedergegeben. Weitere Informationen zu dieser Methode finden Sie unter [Verwenden der Funktion „PlaySound“ mit Wave-Audiodateien](https://docs.microsoft.com/windows/desktop/multimedia/using-playsound-to-play-waveform-audio-files). Suchen Sie nach einer Datei und wählen Sie eine aus, die über eine WAV-Erweiterung verfügt, und klicken Sie anschließend auf **Öffnen**, um die WAVE-Datei mit einem Plattformaufruf wiederzugeben. Der vollständige Pfad der ausgewählten Datei wird in einem Textfeld angezeigt.

Das Dialogfeld **Open Files** (Dateien öffnen) wird so gefiltert, dass es nur Dateien mit WAV-Erweiterung anzeigt werden. Dazu werden folgende Filtereinstellungen verwendet:

[!code-csharp[csProgGuideInterop#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#5)]

[!code-csharp[csProgGuideInterop#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#3)]

## <a name="compiling-the-code"></a>Kompilieren des Codes

1. Erstellen Sie in Visual Studio ein neues C#-Windows Forms-Anwendungsprojekt, und nennen Sie es **WinSound**.

2. Kopieren Sie den oben stehenden Code, und fügen Sie diesen über dem Inhalt der Datei *Form1.cs* ein.

3. Kopieren Sie den folgenden Code, und fügen Sie ihn in der *Form1.Designer.cs*-Datei in der `InitializeComponent()`-Methode immer nach vorhandenem Code ein.

     [!code-csharp[csProgGuideInterop#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#4)]

4. Kompilieren Sie den Code, und führen Sie diesen aus.

## <a name="see-also"></a>Weitere Informationen

- [C#-Programmierhandbuch](../index.md)
- [Überblick über die Interoperabilität](interoperability-overview.md)
- [Genauere Betrachtung von Plattformaufrufen](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [Marshallen von Daten mit Plattformaufruf](../../../framework/interop/marshaling-data-with-platform-invoke.md)
