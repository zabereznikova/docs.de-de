---
description: -errorreport (C#-Compileroptionen)
title: -errorreport (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /errorreport
helpviewer_keywords:
- -errorreport compiler option [C#]
- errorreport compiler option [C#]
- /errorreport compiler option [C#]
ms.assetid: bd0e7493-b79d-4369-9c3f-ba26ebdfbedf
ms.openlocfilehash: 6238ac392ff99d18d9cc7ea07e23b08ff235c14f
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "91173229"
---
# <a name="-errorreport-c-compiler-options"></a><span data-ttu-id="467a3-103">-errorreport (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="467a3-103">-errorreport (C# Compiler Options)</span></span>

<span data-ttu-id="467a3-104">Diese Option bietet eine einfache Möglichkeit, einen internen C#-Compilerfehler an Microsoft zu melden.</span><span class="sxs-lookup"><span data-stu-id="467a3-104">This option provides a convenient way to report a C# internal compiler error to Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="467a3-105">Unter Windows Vista und Windows Server 2008 überschreiben die Einstellungen für die Fehlerberichterstattung, die Sie für Visual Studio festgelegt haben, nicht die Einstellungen, die über Windows-Fehlerberichterstattung (WER) festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="467a3-105">On Windows Vista and Windows Server 2008, the error reporting settings that you make for Visual Studio do not override the settings made through Windows Error Reporting (WER).</span></span> <span data-ttu-id="467a3-106">WER-Einstellungen haben immer Vorrang vor Einstellungen für Fehlerberichterstattung in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="467a3-106">WER settings always take precedence over Visual Studio error reporting settings.</span></span>

## <a name="syntax"></a><span data-ttu-id="467a3-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="467a3-107">Syntax</span></span>

```console
-errorreport:{ none | prompt | queue | send }
```

## <a name="arguments"></a><span data-ttu-id="467a3-108">Argumente</span><span class="sxs-lookup"><span data-stu-id="467a3-108">Arguments</span></span>

 <span data-ttu-id="467a3-109">**keine**</span><span class="sxs-lookup"><span data-stu-id="467a3-109">**none**</span></span>  
 <span data-ttu-id="467a3-110">Berichte zu internen Compilerfehlern werden nicht gesammelt oder an Microsoft gesendet.</span><span class="sxs-lookup"><span data-stu-id="467a3-110">Reports about internal compiler errors will not be collected or sent to Microsoft.</span></span>

 <span data-ttu-id="467a3-111">**prompt**: Sie werden aufgefordert, einen Bericht zu senden, wenn Sie einen internen Compilerfehler erhalten.</span><span class="sxs-lookup"><span data-stu-id="467a3-111">**prompt** Prompts you to send a report when you receive an internal compiler error.</span></span> <span data-ttu-id="467a3-112">**Aufforderung** ist die Standardeinstellung beim Kompilieren einer Anwendung in der Entwicklungsumgebung.</span><span class="sxs-lookup"><span data-stu-id="467a3-112">**prompt** is the default when you compile an application in the development environment.</span></span>

 <span data-ttu-id="467a3-113">**queue**: Der Fehlerbericht wird in die Warteschlange eingereiht.</span><span class="sxs-lookup"><span data-stu-id="467a3-113">**queue** Queues the error report.</span></span> <span data-ttu-id="467a3-114">Wenn Sie sich mit Administratoranmeldeinformationen anmelden, können Sie alle Fehler seit dem letzten Login melden.</span><span class="sxs-lookup"><span data-stu-id="467a3-114">When you log on with administrative credentials, you can report any failures since the last time that you were logged on.</span></span> <span data-ttu-id="467a3-115">Sie werden nicht aufgefordert, Fehlerberichte mehr als einmal alle drei Tage zu senden.</span><span class="sxs-lookup"><span data-stu-id="467a3-115">You will not be prompted to send reports for failures more than once every three days.</span></span> <span data-ttu-id="467a3-116">**Warteschlange** ist die Standardeinstellung, wenn Sie eine Anwendung in der Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="467a3-116">**queue** is the default when you compile an application at the command line.</span></span>

 <span data-ttu-id="467a3-117">**send**: Sendet Berichte zu internen Compilerfehlern automatisch an Microsoft.</span><span class="sxs-lookup"><span data-stu-id="467a3-117">**send** Automatically sends reports of internal compiler errors to Microsoft.</span></span> <span data-ttu-id="467a3-118">Wenn Sie diese Option aktivieren, müssen Sie zuerst der Richtlinie zur Datensammlung von Microsoft zustimmen.</span><span class="sxs-lookup"><span data-stu-id="467a3-118">To enable this option, you must first agree to the Microsoft data collection policy.</span></span> <span data-ttu-id="467a3-119">Beim ersten Mal, wenn Sie **-errorreport:send** auf einem Computer angeben, wird eine Compilermeldung Sie auf eine Website verweisen, die die Microsoft-Richtlinie zur Datensammlung enthält.</span><span class="sxs-lookup"><span data-stu-id="467a3-119">The first time that you specify **-errorreport:send** on a computer, a compiler message will refer you to a Web site that contains the Microsoft data collection policy.</span></span>

## <a name="remarks"></a><span data-ttu-id="467a3-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="467a3-120">Remarks</span></span>

 <span data-ttu-id="467a3-121">Ein interner Compilerfehler (ICE) entsteht, wenn der Compiler eine Quellcodedatei nicht verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="467a3-121">An internal compiler error (ICE) results when the compiler cannot process a source code file.</span></span> <span data-ttu-id="467a3-122">Tritt ein ICE auf, erzeugt der Compiler keine Ausgabedatei oder eine hilfreiche Diagnose, die Sie verwenden können, um Ihren Code zu beheben.</span><span class="sxs-lookup"><span data-stu-id="467a3-122">When an ICE occurs, the compiler does not produce an output file or any useful diagnostic that you can use to fix your code.</span></span>

 <span data-ttu-id="467a3-123">In früheren Versionen wurden Sie beim Auftreten eines ICE aufgefordert, sich an den Microsoft-Produktsupport zu wenden, um das Problem zu melden.</span><span class="sxs-lookup"><span data-stu-id="467a3-123">In previous releases, when you received an ICE, you were encouraged to contact Microsoft Product Support Services to report the problem.</span></span> <span data-ttu-id="467a3-124">Mithilfe von **-errorreport** können Sie dem Visual C#-Team ICE-Informationen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="467a3-124">By using **-errorreport**, you can provide ICE information to the Visual C# team.</span></span> <span data-ttu-id="467a3-125">Die Fehlerberichte können dabei helfen, zukünftige Compilerversionen zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="467a3-125">Your error reports can help improve future compiler releases.</span></span>

 <span data-ttu-id="467a3-126">Die Fähigkeit eines Benutzers zum Senden von Berichten hängt vom Computer und den Benutzerberechtigungen ab.</span><span class="sxs-lookup"><span data-stu-id="467a3-126">A user's ability to send reports depends on computer and user policy permissions.</span></span>

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="467a3-127">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="467a3-127">To set this compiler option in the Visual Studio development environment</span></span>

1. <span data-ttu-id="467a3-128">Öffnen Sie die Seite **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="467a3-128">Open the project's **Properties** page.</span></span> <span data-ttu-id="467a3-129">Weitere Informationen finden Sie unter [Seite „Erstellen“, Projekt-Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="467a3-129">For more information, see [Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span></span>

2. <span data-ttu-id="467a3-130">Klicken Sie auf die Eigenschaftenseite **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="467a3-130">Click the **Build** property page.</span></span>

3. <span data-ttu-id="467a3-131">Klicken Sie auf die Schaltfläche **Erweitert** .</span><span class="sxs-lookup"><span data-stu-id="467a3-131">Click the **Advanced** button.</span></span>

4. <span data-ttu-id="467a3-132">Ändern Sie die Eigenschaft **Bericht für internen Compilerfehler**.</span><span class="sxs-lookup"><span data-stu-id="467a3-132">Modify the **Internal Compiler Error Reporting** property.</span></span>

 <span data-ttu-id="467a3-133">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.ErrorReport%2A>.</span><span class="sxs-lookup"><span data-stu-id="467a3-133">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.ErrorReport%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="467a3-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="467a3-134">See also</span></span>

- [<span data-ttu-id="467a3-135">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="467a3-135">C# Compiler Options</span></span>](./index.md)
