---
title: 'Gewusst wie: Verwenden eines Plattformaufrufs zum Wiedergeben einer Wavedatei (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- platform invoke, sound files
- interoperability [C#], playing WAV files using pinvoke
- wav files
- .wav files
ms.assetid: f7f62f53-e026-4c40-b221-3a26adb0c2c5
caps.latest.revision: 30
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 001236392d2b3d3c70dbd0faf2a899929dfe8625
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-platform-invoke-to-play-a-wave-file-c-programming-guide"></a><span data-ttu-id="4133d-102">Gewusst wie: Verwenden eines Plattformaufrufs zum Wiedergeben einer Wavedatei (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="4133d-102">How to: Use Platform Invoke to Play a Wave File (C# Programming Guide)</span></span>
<span data-ttu-id="4133d-103">In folgendem C#-Codebeispiel wird die Verwendung von Plattformaufrufdiensten zum Abspielen einer Audiodatei im Waveformat im Windows-Betriebssystem veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="4133d-103">The following C# code example illustrates how to use platform invoke services to play a wave sound file on the Windows operating system.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4133d-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4133d-104">Example</span></span>  
 <span data-ttu-id="4133d-105">In diesem Beispielcode wird `DllImport` verwendet, um den Einstiegspunkt der `PlaySound`-Methode von `winmm.dll` als `Form1 PlaySound()` zu importieren.</span><span class="sxs-lookup"><span data-stu-id="4133d-105">This example code uses `DllImport` to import `winmm.dll`'s `PlaySound` method entry point as `Form1 PlaySound()`.</span></span> <span data-ttu-id="4133d-106">Das Beispiel hat ein einfaches Windows-Formular mit einer Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="4133d-106">The example has a simple Windows Form with a button.</span></span> <span data-ttu-id="4133d-107">Wenn Sie auf die Schaltfläche klicken, öffnet sich das Windows-Standarddialogfeld <xref:System.Windows.Forms.OpenFileDialog>, von wo aus Sie eine Datei zur Wiedergabe öffnen können.</span><span class="sxs-lookup"><span data-stu-id="4133d-107">Clicking the button opens a standard windows <xref:System.Windows.Forms.OpenFileDialog> dialog box so that you can open a file to play.</span></span> <span data-ttu-id="4133d-108">Wenn Sie eine Wavedatei auswählen, wird diese mit der `PlaySound()`-Methode der Assemblymethode „wimm.dll“ wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="4133d-108">When a wave file is selected, it is played by using the `PlaySound()` method of the winmm.DLL assembly method.</span></span> <span data-ttu-id="4133d-109">Weitere Informationen zur `PlaySound`-Methode von „winmm.dll“ finden Sie unter [Using the PlaySound function with Waveform-Audio Files (Verwenden der Funktion „PlaySound“ mit WAVE-Audiodateien)](http://go.microsoft.com/fwlink/?LinkId=148553).</span><span class="sxs-lookup"><span data-stu-id="4133d-109">For more information about winmm.dll's `PlaySound` method, see [Using the PlaySound function with Waveform-Audio Files](http://go.microsoft.com/fwlink/?LinkId=148553).</span></span> <span data-ttu-id="4133d-110">Suchen Sie nach einer Datei und wählen Sie eine aus, die über eine WAV-Erweiterung verfügt, und klicken Sie anschließend auf **Öffnen**, um die WAVE-Datei mit einem Plattformaufruf wiederzugeben.</span><span class="sxs-lookup"><span data-stu-id="4133d-110">Browse and select a file that has a .wav extension, and then click **Open** to play the wave file by using platform invoke.</span></span> <span data-ttu-id="4133d-111">Der vollständige Pfad der ausgewählten Datei wird in einem Textfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4133d-111">A text box shows the full path of the file selected.</span></span>  
  
 <span data-ttu-id="4133d-112">Das Dialogfeld **Open Files** (Dateien öffnen) wird so gefiltert, dass es nur Dateien mit WAV-Erweiterung anzeigt werden. Dazu werden folgende Filtereinstellungen verwendet:</span><span class="sxs-lookup"><span data-stu-id="4133d-112">The **Open Files** dialog box is filtered to show only files that have a .wav extension through the filter settings:</span></span>  
  
 <span data-ttu-id="4133d-113">[!code-cs[csProgGuideInterop#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="4133d-113">[!code-cs[csProgGuideInterop#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_1.cs)]</span></span>  
  
 <span data-ttu-id="4133d-114">[!code-cs[csProgGuideInterop#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="4133d-114">[!code-cs[csProgGuideInterop#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_2.cs)]</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4133d-115">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="4133d-115">Compiling the Code</span></span>  
  
### <a name="to-compile-the-code"></a><span data-ttu-id="4133d-116">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="4133d-116">To compile the code</span></span>  
  
1.  <span data-ttu-id="4133d-117">Erstellen Sie in Visual Studio ein neuen Windows-Anwendungsprojekt mit C# und nennen Sie es **WinSound**.</span><span class="sxs-lookup"><span data-stu-id="4133d-117">Create a new C# Windows Application project in Visual Studio and name it **WinSound**.</span></span>  
  
2.  <span data-ttu-id="4133d-118">Kopieren Sie den oben stehenden Code, und fügen Sie diesen über dem Inhalt der `Form1.cs`-Datei ein.</span><span class="sxs-lookup"><span data-stu-id="4133d-118">Copy the code above, and paste it over the contents of the `Form1.cs` file.</span></span>  
  
3.  <span data-ttu-id="4133d-119">Kopieren Sie folgenden Code und fügen Sie ihn in der `Form1.Designer.cs`-Datei in der `InitializeComponent()`-Methode ein, und zwar immer nach vorhandenem Code.</span><span class="sxs-lookup"><span data-stu-id="4133d-119">Copy the following code, and paste it in the `Form1.Designer.cs` file, in the `InitializeComponent()` method, after any existing code.</span></span>  
  
     <span data-ttu-id="4133d-120">[!code-cs[csProgGuideInterop#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="4133d-120">[!code-cs[csProgGuideInterop#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_3.cs)]</span></span>  
  
4.  <span data-ttu-id="4133d-121">Kompilieren Sie den Code, und führen Sie diesen aus.</span><span class="sxs-lookup"><span data-stu-id="4133d-121">Compile and run the code.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="4133d-122">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="4133d-122">.NET Framework Security</span></span>  
 <span data-ttu-id="4133d-123">Weitere Informationen finden Sie unter [.NET Framework-Sicherheit](http://go.microsoft.com/fwlink/?LinkId=37122).</span><span class="sxs-lookup"><span data-stu-id="4133d-123">For more information, see [.NET Framework Security](http://go.microsoft.com/fwlink/?LinkId=37122).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4133d-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4133d-124">See Also</span></span>  
 <span data-ttu-id="4133d-125">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="4133d-125">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="4133d-126">[Überblick über die Interoperabilität](../../../csharp/programming-guide/interop/interoperability-overview.md) </span><span class="sxs-lookup"><span data-stu-id="4133d-126">[Interoperability Overview](../../../csharp/programming-guide/interop/interoperability-overview.md) </span></span>  
 <span data-ttu-id="4133d-127">[Überblick über die Interoperabilität](../../../csharp/programming-guide/interop/interoperability-overview.md) </span><span class="sxs-lookup"><span data-stu-id="4133d-127">[Interoperability Overview](../../../csharp/programming-guide/interop/interoperability-overview.md) </span></span>  
 <span data-ttu-id="4133d-128">[Genauere Betrachtung von Plattformaufrufen](http://msdn.microsoft.com/en-us/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243) </span><span class="sxs-lookup"><span data-stu-id="4133d-128">[A Closer Look at Platform Invoke](http://msdn.microsoft.com/en-us/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243) </span></span>  
 [<span data-ttu-id="4133d-129">Marshallen von Daten mit Plattformaufruf</span><span class="sxs-lookup"><span data-stu-id="4133d-129">Marshaling Data with Platform Invoke</span></span>](../../../framework/interop/marshaling-data-with-platform-invoke.md)

