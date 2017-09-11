---
title: -errorreport (C#-Compileroptionen)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /errorreport
dev_langs:
- CSharp
helpviewer_keywords:
- -errorreport compiler option [C#]
- errorreport compiler option [C#]
- /errorreport compiler option [C#]
ms.assetid: bd0e7493-b79d-4369-9c3f-ba26ebdfbedf
caps.latest.revision: 35
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
ms.openlocfilehash: d32ec08da36509527b153166ae15019f129aad71
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="errorreport-c-compiler-options"></a><span data-ttu-id="5504b-102">/errorreport (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="5504b-102">/errorreport (C# Compiler Options)</span></span>
<span data-ttu-id="5504b-103">Diese Option bietet eine einfache Möglichkeit, einen internen C#-Compilerfehler an Microsoft zu melden.</span><span class="sxs-lookup"><span data-stu-id="5504b-103">This option provides a convenient way to report a C# internal compiler error to Microsoft.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5504b-104">Unter Windows Vista und Windows Server 2008 überschreiben die Einstellungen für die Fehlerberichterstattung, die Sie für Visual Studio festgelegt haben, nicht die Einstellungen, die über Windows-Fehlerberichterstattung (WER) festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="5504b-104">On Windows Vista and Windows Server 2008, the error reporting settings that you make for Visual Studio do not override the settings made through Windows Error Reporting (WER).</span></span> <span data-ttu-id="5504b-105">WER-Einstellungen haben immer Vorrang vor Einstellungen für Fehlerberichterstattung in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5504b-105">WER settings always take precedence over Visual Studio error reporting settings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5504b-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="5504b-106">Syntax</span></span>  
  
```console  
/errorreport:{ none | prompt | queue | send }  
```  
  
## <a name="arguments"></a><span data-ttu-id="5504b-107">Argumente</span><span class="sxs-lookup"><span data-stu-id="5504b-107">Arguments</span></span>  
 <span data-ttu-id="5504b-108">**none**</span><span class="sxs-lookup"><span data-stu-id="5504b-108">**none**</span></span>  
 <span data-ttu-id="5504b-109">Berichte zu internen Compilerfehlern werden nicht gesammelt oder an Microsoft gesendet.</span><span class="sxs-lookup"><span data-stu-id="5504b-109">Reports about internal compiler errors will not be collected or sent to Microsoft.</span></span>  
  
 <span data-ttu-id="5504b-110">**Aufforderung**</span><span class="sxs-lookup"><span data-stu-id="5504b-110">**prompt**</span></span>  
 <span data-ttu-id="5504b-111">Sie werden aufgefordert, einen Bericht zu senden, wenn Sie einen internen Compilerfehler empfangen.</span><span class="sxs-lookup"><span data-stu-id="5504b-111">Prompts you to send a report when you receive an internal compiler error.</span></span> <span data-ttu-id="5504b-112">**Aufforderung** ist die Standardeinstellung beim Kompilieren einer Anwendung in der Entwicklungsumgebung.</span><span class="sxs-lookup"><span data-stu-id="5504b-112">**prompt** is the default when you compile an application in the development environment.</span></span>  
  
 <span data-ttu-id="5504b-113">**Warteschlange**</span><span class="sxs-lookup"><span data-stu-id="5504b-113">**queue**</span></span>  
 <span data-ttu-id="5504b-114">Der Fehlerbericht wird in die Warteschlange gesetzt.</span><span class="sxs-lookup"><span data-stu-id="5504b-114">Queues the error report.</span></span> <span data-ttu-id="5504b-115">Wenn Sie sich mit Administratoranmeldeinformationen anmelden, können Sie alle Fehler seit dem letzten Login melden.</span><span class="sxs-lookup"><span data-stu-id="5504b-115">When you log on with administrative credentials, you can report any failures since the last time that you were logged on.</span></span> <span data-ttu-id="5504b-116">Sie werden nicht aufgefordert, Fehlerberichte mehr als einmal alle drei Tage zu senden.</span><span class="sxs-lookup"><span data-stu-id="5504b-116">You will not be prompted to send reports for failures more than once every three days.</span></span> <span data-ttu-id="5504b-117">**Warteschlange** ist die Standardeinstellung, wenn Sie eine Anwendung in der Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="5504b-117">**queue** is the default when you compile an application at the command line.</span></span>  
  
 <span data-ttu-id="5504b-118">**Senden**</span><span class="sxs-lookup"><span data-stu-id="5504b-118">**send**</span></span>  
 <span data-ttu-id="5504b-119">Sendet Berichte über interne Compilerfehler automatisch an Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5504b-119">Automatically sends reports of internal compiler errors to Microsoft.</span></span> <span data-ttu-id="5504b-120">Wenn Sie diese Option aktivieren, müssen Sie zuerst der Richtlinie zur Datensammlung von Microsoft zustimmen.</span><span class="sxs-lookup"><span data-stu-id="5504b-120">To enable this option, you must first agree to the Microsoft data collection policy.</span></span> <span data-ttu-id="5504b-121">Beim ersten Mal, wenn Sie **/errorreport:send** auf einem Computer angeben, wird eine Compilermeldung Sie auf eine Website verweisen, die die Microsoft-Richtlinie zur Datensammlung enthält.</span><span class="sxs-lookup"><span data-stu-id="5504b-121">The first time that you specify **/errorreport:send** on a computer, a compiler message will refer you to a Web site that contains the Microsoft data collection policy.</span></span>  
  
 <span data-ttu-id="5504b-122">Diese Option hängt von Registrierungseinstellungen ab.</span><span class="sxs-lookup"><span data-stu-id="5504b-122">This option depends on registry settings.</span></span> <span data-ttu-id="5504b-123">Informationen dazu, wie Sie die entsprechenden Werte in der Registrierung festlegen, finden Sie unter [How to Turn on Automatic Error Reporting in Visual Studio 2008 Command-line Tools (Aktivieren der automatischen Fehlerberichterstattung in Visual Studio 2008-Befehlszeilentools)](http://go.microsoft.com/fwlink/?LinkID=184695) auf der MSDN-Website.</span><span class="sxs-lookup"><span data-stu-id="5504b-123">For information about how to set the appropriate values in the registry, see [How to Turn on Automatic Error Reporting in Visual Studio 2008 Command-line Tools](http://go.microsoft.com/fwlink/?LinkID=184695) on the MSDN Web site.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5504b-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5504b-124">Remarks</span></span>  
 <span data-ttu-id="5504b-125">Ein interner Compilerfehler (ICE) entsteht, wenn der Compiler eine Quellcodedatei nicht verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="5504b-125">An internal compiler error (ICE) results when the compiler cannot process a source code file.</span></span> <span data-ttu-id="5504b-126">Tritt ein ICE auf, erzeugt der Compiler keine Ausgabedatei oder eine hilfreiche Diagnose, die Sie verwenden können, um Ihren Code zu beheben.</span><span class="sxs-lookup"><span data-stu-id="5504b-126">When an ICE occurs, the compiler does not produce an output file or any useful diagnostic that you can use to fix your code.</span></span>  
  
 <span data-ttu-id="5504b-127">In früheren Versionen wurden Sie beim Auftreten eines ICE aufgefordert, sich an den Microsoft-Produktsupport zu wenden, um das Problem zu melden.</span><span class="sxs-lookup"><span data-stu-id="5504b-127">In previous releases, when you received an ICE, you were encouraged to contact Microsoft Product Support Services to report the problem.</span></span> <span data-ttu-id="5504b-128">Mithilfe von **/errorreport** können Sie dem Visual C#-Team ICE-Informationen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="5504b-128">By using **/errorreport**, you can provide ICE information to the Visual C# team.</span></span> <span data-ttu-id="5504b-129">Die Fehlerberichte können dabei helfen, zukünftige Compilerversionen zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="5504b-129">Your error reports can help improve future compiler releases.</span></span>  
  
 <span data-ttu-id="5504b-130">Die Fähigkeit eines Benutzers zum Senden von Berichten hängt vom Computer und den Benutzerberechtigungen ab.</span><span class="sxs-lookup"><span data-stu-id="5504b-130">A user's ability to send reports depends on computer and user policy permissions.</span></span>  
  
 <span data-ttu-id="5504b-131">Weitere Informationen zum Fehlerdebugger finden Sie unter [Beschreibung des Dr. Watson für Windows (Drwtsn32.exe)-Tool](http://go.microsoft.com/fwlink/?LinkId=147286).</span><span class="sxs-lookup"><span data-stu-id="5504b-131">For more information about error debugger, see [Description of the Dr. Watson for Windows (Drwtsn32.exe) Tool](http://go.microsoft.com/fwlink/?LinkId=147286).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="5504b-132">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="5504b-132">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="5504b-133">Öffnen Sie die **Eigenschaftenseite** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="5504b-133">Open the project's **Properties** page.</span></span> <span data-ttu-id="5504b-134">Weitere Informationen finden Sie unter [Seite „Erstellen“, Projekt-Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="5504b-134">For more information, see [Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span></span>  
  
2.  <span data-ttu-id="5504b-135">Klicken Sie auf die Eigenschaftenseite **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="5504b-135">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="5504b-136">Klicken Sie auf die Schaltfläche **Erweitert** .</span><span class="sxs-lookup"><span data-stu-id="5504b-136">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="5504b-137">Ändern Sie die Eigenschaft **Bericht für internen Compilerfehler**.</span><span class="sxs-lookup"><span data-stu-id="5504b-137">Modify the **Internal Compiler Error Reporting** property.</span></span>  
  
 <span data-ttu-id="5504b-138">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.ErrorReport%2A>.</span><span class="sxs-lookup"><span data-stu-id="5504b-138">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.ErrorReport%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5504b-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5504b-139">See Also</span></span>  
 [<span data-ttu-id="5504b-140">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="5504b-140">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)

