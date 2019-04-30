---
title: Technologiebeispiel für versionstolerante Serialisierung
ms.date: 03/30/2017
ms.assetid: 2a183664-bfbf-4ff0-96f6-c836284ea916
ms.openlocfilehash: d7dfcf7548571d29032495ca8be96db70f2336fc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62028264"
---
# <a name="version-tolerant-serialization-technology-sample"></a><span data-ttu-id="ae0ec-102">Technologiebeispiel für versionstolerante Serialisierung</span><span class="sxs-lookup"><span data-stu-id="ae0ec-102">Version Tolerant Serialization Technology Sample</span></span>
[<span data-ttu-id="ae0ec-103">Beispiel herunterladen</span><span class="sxs-lookup"><span data-stu-id="ae0ec-103">Download Sample</span></span>](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Runtime%20Serialization/VTS.zip.exe)  
  
 <span data-ttu-id="ae0ec-104">In diesem Beispiel werden die Funktionen für die Versionstoleranz von .NET Serialisierung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ae0ec-104">This sample demonstrates the version tolerance features of .NET Serialization.</span></span> <span data-ttu-id="ae0ec-105">Im Beispiel werden Anwendungen erstellt, die zum Serialisieren und Deserialisieren von Daten andere Versionen von <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> verwenden.</span><span class="sxs-lookup"><span data-stu-id="ae0ec-105">The sample builds applications that use different versions of a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> to serialize and deserialize data.</span></span> <span data-ttu-id="ae0ec-106">Obwohl verschiedene Typversionen verwendet werden, kommunizieren die Anwendungen reibungslos miteinander.</span><span class="sxs-lookup"><span data-stu-id="ae0ec-106">Despite the presence of different type versions, the applications communicate seamlessly.</span></span> <span data-ttu-id="ae0ec-107">Weitere Informationen finden Sie unter [Versionstolerante Serialisierung](../../../docs/standard/serialization/version-tolerant-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="ae0ec-107">For more information, see [Version Tolerant Serialization](../../../docs/standard/serialization/version-tolerant-serialization.md).</span></span>  
  
### <a name="to-build-the-sample-using-the-command-prompt"></a><span data-ttu-id="ae0ec-108">So erstellen Sie das Beispiel mithilfe der Eingabeaufforderung</span><span class="sxs-lookup"><span data-stu-id="ae0ec-108">To build the sample using the command prompt</span></span>  
  
1. <span data-ttu-id="ae0ec-109">Öffnen Sie ein Eingabeaufforderungsfenster, und navigieren Sie zu einem der sprachspezifischen Unterverzeichnisse (unter V1 Application oder V2 Application) für das Beispiel.</span><span class="sxs-lookup"><span data-stu-id="ae0ec-109">Open a Command Prompt window and navigate to one of the language-specific subdirectories (under V1 Application or V2 Application) for the sample.</span></span>  
  
2. <span data-ttu-id="ae0ec-110">Geben Sie in die Befehlszeile **msbuild.exe \<ver> application.sln** ein (wobei „\<ver>“ entweder v1 oder v2 entspricht).</span><span class="sxs-lookup"><span data-stu-id="ae0ec-110">Type **msbuild.exe \<ver> application.sln** at the command line (where \<ver> is either v1 or v2).</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="ae0ec-111">So erstellen Sie das Beispiel mithilfe von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ae0ec-111">To build the sample using Visual Studio</span></span>  
  
1. <span data-ttu-id="ae0ec-112">Öffnen Sie [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)], und navigieren Sie zu einem der sprachspezifischen Unterverzeichnisse für das Beispiel.</span><span class="sxs-lookup"><span data-stu-id="ae0ec-112">Open [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2. <span data-ttu-id="ae0ec-113">Navigieren Sie zum Unterverzeichnis V1 Application in dem Verzeichnis, das Sie im vorherigen Schritt ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="ae0ec-113">Navigate to the V1 Application subdirectory of the directory you selected in the previous step.</span></span>  
  
3. <span data-ttu-id="ae0ec-114">Doppelklicken Sie auf das Symbol für V1 Application.sln, um die Datei in Visual Studio zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ae0ec-114">Double-click the icon for V1 Application.sln to open the file in Visual Studio.</span></span>  
  
4. <span data-ttu-id="ae0ec-115">Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.</span><span class="sxs-lookup"><span data-stu-id="ae0ec-115">On the **Build** menu, click **Build Solution**.</span></span>  
  
5. <span data-ttu-id="ae0ec-116">Navigieren Sie zum Unterverzeichnis V2 Application, und wiederholen Sie die beiden vorherigen Schritte, um die V2-Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ae0ec-116">Navigate to the V2 Application subdirectory and repeat the two previous steps to build the V2 Application.</span></span>  
  
 <span data-ttu-id="ae0ec-117">Die Anwendungen werden im Standardunterverzeichnis \bin oder \bin\Debug des zugehörigen Projektverzeichnisses erstellt.</span><span class="sxs-lookup"><span data-stu-id="ae0ec-117">The applications will be built in the default \bin or \bin\Debug subdirectories of their respective project directories.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="ae0ec-118">So führen Sie das Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="ae0ec-118">To run the sample</span></span>  
  
1. <span data-ttu-id="ae0ec-119">Navigieren Sie im Eingabeaufforderungsfenster zu dem sprachspezifischen Unterverzeichnis, das Sie beim Erstellen der Beispielanwendungen ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="ae0ec-119">In the Command Prompt window, navigate to the language-specific subdirectory that you selected when you built the sample applications.</span></span>  
  
2. <span data-ttu-id="ae0ec-120">Geben Sie **runme.cmd** in der Befehlszeile ein, um sofort beide Anwendungen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ae0ec-120">Type **runme.cmd** at the command line to run both applications at once.</span></span>  
  
 <span data-ttu-id="ae0ec-121">Alternativ können Sie zu den Verzeichnissen navigieren, die die neuen ausführbaren Dateien enthalten, und diese dann nacheinander ausführen.</span><span class="sxs-lookup"><span data-stu-id="ae0ec-121">Alternatively, navigate to the directories that contain the new executables and run them sequentially.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae0ec-122">In diesem Beispiel werden Konsolenanwendungen erstellt.</span><span class="sxs-lookup"><span data-stu-id="ae0ec-122">The sample builds console applications.</span></span> <span data-ttu-id="ae0ec-123">Sie müssen diese in einem Eingabeaufforderungsfenster starten und ausführen, um die Ausgabe anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ae0ec-123">You must launch and run them in a Command Prompt window to view their output.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae0ec-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae0ec-124">See also</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>
- <xref:System.IO.FileStream>
