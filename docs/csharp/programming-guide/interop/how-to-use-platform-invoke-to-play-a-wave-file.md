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
ms.openlocfilehash: 6f507fa348bf1ea1b3fc5c3a868a6fbab7f8ec56
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558354"
---
# <a name="how-to-use-platform-invoke-to-play-a-wav-file-c-programming-guide"></a><span data-ttu-id="ba566-103">Vorgehensweise: Verwenden eines Plattformaufrufs zum Wiedergeben einer WAV-Datei (C#-Programmierleitfaden)</span><span class="sxs-lookup"><span data-stu-id="ba566-103">How to use platform invoke to play a WAV file (C# Programming Guide)</span></span>

<span data-ttu-id="ba566-104">Im folgenden C#-Codebeispiel wird die Verwendung von Plattformaufrufdiensten zum Wiedergeben einer WAV-Audiodatei unter dem Betriebssystem Windows veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ba566-104">The following C# code example illustrates how to use platform invoke services to play a WAV sound file on the Windows operating system.</span></span>

## <a name="example"></a><span data-ttu-id="ba566-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ba566-105">Example</span></span>

<span data-ttu-id="ba566-106">In diesem Beispielcode wird <xref:System.Runtime.InteropServices.DllImportAttribute> verwendet, um den Einstiegspunkt der `PlaySound`-Methode von `winmm.dll` als `Form1 PlaySound()` zu importieren.</span><span class="sxs-lookup"><span data-stu-id="ba566-106">This example code uses <xref:System.Runtime.InteropServices.DllImportAttribute> to import `winmm.dll`'s `PlaySound` method entry point as `Form1 PlaySound()`.</span></span> <span data-ttu-id="ba566-107">Das Beispiel hat ein einfaches Windows-Formular mit einer Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="ba566-107">The example has a simple Windows Form with a button.</span></span> <span data-ttu-id="ba566-108">Wenn Sie auf die Schaltfläche klicken, öffnet sich das Windows-Standarddialogfeld <xref:System.Windows.Forms.OpenFileDialog>, von wo aus Sie eine Datei zur Wiedergabe öffnen können.</span><span class="sxs-lookup"><span data-stu-id="ba566-108">Clicking the button opens a standard windows <xref:System.Windows.Forms.OpenFileDialog> dialog box so that you can open a file to play.</span></span> <span data-ttu-id="ba566-109">Wenn Sie eine Wavedatei auswählen, wird diese mit der `PlaySound()`-Methode der *wimm.dll*-Bibliothek wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="ba566-109">When a wave file is selected, it is played by using the `PlaySound()` method of the *winmm.dll* library.</span></span> <span data-ttu-id="ba566-110">Weitere Informationen zu dieser Methode finden Sie unter [Verwenden der Funktion „PlaySound“ mit Wave-Audiodateien](/windows/desktop/multimedia/using-playsound-to-play-waveform-audio-files).</span><span class="sxs-lookup"><span data-stu-id="ba566-110">For more information about this method, see [Using the PlaySound function with Waveform-Audio Files](/windows/desktop/multimedia/using-playsound-to-play-waveform-audio-files).</span></span> <span data-ttu-id="ba566-111">Suchen Sie nach einer Datei und wählen Sie eine aus, die über eine WAV-Erweiterung verfügt, und klicken Sie anschließend auf **Öffnen**, um die WAVE-Datei mit einem Plattformaufruf wiederzugeben.</span><span class="sxs-lookup"><span data-stu-id="ba566-111">Browse and select a file that has a .wav extension, and then click **Open** to play the wave file by using platform invoke.</span></span> <span data-ttu-id="ba566-112">Der vollständige Pfad der ausgewählten Datei wird in einem Textfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ba566-112">A text box shows the full path of the file selected.</span></span>

<span data-ttu-id="ba566-113">Das Dialogfeld **Open Files** (Dateien öffnen) wird so gefiltert, dass es nur Dateien mit WAV-Erweiterung anzeigt werden. Dazu werden folgende Filtereinstellungen verwendet:</span><span class="sxs-lookup"><span data-stu-id="ba566-113">The **Open Files** dialog box is filtered to show only files that have a .wav extension through the filter settings:</span></span>

[!code-csharp[csProgGuideInterop#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#5)]

[!code-csharp[csProgGuideInterop#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#3)]

## <a name="compiling-the-code"></a><span data-ttu-id="ba566-114">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="ba566-114">Compiling the code</span></span>

1. <span data-ttu-id="ba566-115">Erstellen Sie in Visual Studio ein neues C#-Windows Forms-Anwendungsprojekt, und nennen Sie es **WinSound**.</span><span class="sxs-lookup"><span data-stu-id="ba566-115">Create a new C# Windows Forms Application project in Visual Studio and name it **WinSound**.</span></span>

2. <span data-ttu-id="ba566-116">Kopieren Sie den oben stehenden Code, und fügen Sie diesen über dem Inhalt der Datei *Form1.cs* ein.</span><span class="sxs-lookup"><span data-stu-id="ba566-116">Copy the code above, and paste it over the contents of the *Form1.cs* file.</span></span>

3. <span data-ttu-id="ba566-117">Kopieren Sie den folgenden Code, und fügen Sie ihn in der *Form1.Designer.cs*-Datei in der `InitializeComponent()`-Methode immer nach vorhandenem Code ein.</span><span class="sxs-lookup"><span data-stu-id="ba566-117">Copy the following code, and paste it in the *Form1.Designer.cs* file, in the `InitializeComponent()` method, after any existing code.</span></span>

     [!code-csharp[csProgGuideInterop#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#4)]

4. <span data-ttu-id="ba566-118">Kompilieren Sie den Code, und führen Sie diesen aus.</span><span class="sxs-lookup"><span data-stu-id="ba566-118">Compile and run the code.</span></span>

## <a name="see-also"></a><span data-ttu-id="ba566-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ba566-119">See also</span></span>

- [<span data-ttu-id="ba566-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ba566-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ba566-121">Überblick über die Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="ba566-121">Interoperability Overview</span></span>](interoperability-overview.md)
- [<span data-ttu-id="ba566-122">Genauere Betrachtung von Plattformaufrufen</span><span class="sxs-lookup"><span data-stu-id="ba566-122">A Closer Look at Platform Invoke</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [<span data-ttu-id="ba566-123">Marshallen von Daten mit Plattformaufruf</span><span class="sxs-lookup"><span data-stu-id="ba566-123">Marshaling Data with Platform Invoke</span></span>](../../../framework/interop/marshaling-data-with-platform-invoke.md)
