---
title: -bugreport
ms.date: 03/08/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 766a4252fd77be95e2641239cba53a4d90e0cb1d
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2018
---
# <a name="-bugreport"></a><span data-ttu-id="b7d45-102">-bugreport</span><span class="sxs-lookup"><span data-stu-id="b7d45-102">-bugreport</span></span>
<span data-ttu-id="b7d45-103">Erstellt eine Datei, die Sie verwenden können, wenn Sie einen Fehlerbericht einreichen.</span><span class="sxs-lookup"><span data-stu-id="b7d45-103">Creates a file that you can use when you file a bug report.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7d45-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b7d45-104">Syntax</span></span>  
  
```  
-bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="b7d45-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="b7d45-105">Arguments</span></span>  
  
|<span data-ttu-id="b7d45-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="b7d45-106">Term</span></span>|<span data-ttu-id="b7d45-107">Definition</span><span class="sxs-lookup"><span data-stu-id="b7d45-107">Definition</span></span>|  
|---|---|  
|`file`|<span data-ttu-id="b7d45-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b7d45-108">Required.</span></span> <span data-ttu-id="b7d45-109">Der Name der Datei, die den Problembericht enthalten wird.</span><span class="sxs-lookup"><span data-stu-id="b7d45-109">The name of the file that will contain your bug report.</span></span> <span data-ttu-id="b7d45-110">Setzen Sie den Dateinamen in Anführungszeichen (""), wenn der Name ein Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="b7d45-110">Enclose the file name in quotation marks (" ") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7d45-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b7d45-111">Remarks</span></span>  
 <span data-ttu-id="b7d45-112">Die folgende Informationen hinzugefügt `file`:</span><span class="sxs-lookup"><span data-stu-id="b7d45-112">The following information is added to `file`:</span></span>  
  
-   <span data-ttu-id="b7d45-113">Eine Kopie des alle Quellcodedateien in der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="b7d45-113">A copy of all source-code files in the compilation.</span></span>  
  
-   <span data-ttu-id="b7d45-114">Eine Liste der Compileroptionen, die in der Kompilierung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b7d45-114">A list of the compiler options used in the compilation.</span></span>  
  
-   <span data-ttu-id="b7d45-115">Versionsinformationen zur Compiler, common Language Runtime und Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="b7d45-115">Version information about your compiler, common language runtime, and operating system.</span></span>  
  
-   <span data-ttu-id="b7d45-116">Compilerausgabe, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="b7d45-116">Compiler output, if any.</span></span>  
  
-   <span data-ttu-id="b7d45-117">Eine Beschreibung des Problems ist, für die Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="b7d45-117">A description of the problem, for which you are prompted.</span></span>  
  
-   <span data-ttu-id="b7d45-118">Eine Beschreibung, wie Sie das Problem vermuten sollten korrigiert werden, für die Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="b7d45-118">A description of how you think the problem should be fixed, for which you are prompted.</span></span>  
  
 <span data-ttu-id="b7d45-119">Da eine Kopie für alle Quellcodedateien in enthalten ist `file`, Sie möchten den (vermuteten) Codefehler in der kürzestmöglichen Programm zu reproduzieren.</span><span class="sxs-lookup"><span data-stu-id="b7d45-119">Because a copy of all source-code files is included in `file`, you may want to reproduce the (suspected) code defect in the shortest possible program.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b7d45-120">Die `-bugreport` Option erstellt eine Datei, die möglicherweise vertrauliche Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="b7d45-120">The `-bugreport` option produces a file that contains potentially sensitive information.</span></span> <span data-ttu-id="b7d45-121">Dies schließt die aktuelle Uhrzeit, Compilerversion, [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Version, Betriebssystemversion, Benutzername, die Befehlszeilenargumente, mit denen der Compiler ausgeführt wurde, werden alle Quellcode, und die binäre Form eines referenzierten Assemblys.</span><span class="sxs-lookup"><span data-stu-id="b7d45-121">This includes current time, compiler version, [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] version, OS version, user name, the command-line arguments with which the compiler was run, all source code, and the binary form of any referenced assembly.</span></span> <span data-ttu-id="b7d45-122">Diese Option kann zugegriffen werden, durch Angabe von Befehlszeilenoptionen in der Datei "Web.config" für eine serverseitige Kompilierung einer [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] Anwendung.</span><span class="sxs-lookup"><span data-stu-id="b7d45-122">This option can be accessed by specifying command-line options in the Web.config file for a server-side compilation of an [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] application.</span></span> <span data-ttu-id="b7d45-123">Um dies zu verhindern, ändern Sie die Datei "Machine.config", um Benutzer an der Kompilierung auf dem Server zu unterbinden.</span><span class="sxs-lookup"><span data-stu-id="b7d45-123">To prevent this, modify the Machine.config file to disallow users from compiling on the server.</span></span>  
  
 <span data-ttu-id="b7d45-124">Wenn diese Option verwendet wird, mit `-errorreport:prompt`, `-errorreport:queue`, oder `-errorreport:send`, und die Anwendung erkennt, die Informationen in einen interner Compilerfehler `file` wird gesendet, um Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="b7d45-124">If this option is used with `-errorreport:prompt`, `-errorreport:queue`, or `-errorreport:send`, and your application encounters an internal compiler error, the information in `file` is sent to Microsoft Corporation.</span></span> <span data-ttu-id="b7d45-125">Diese Informationen helfen Microsoft-Experten, die die Ursache des Fehlers zu identifizieren und die nächste Version von zu verbessern [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b7d45-125">That information will help Microsoft engineers identify the cause of the error and may help improve the next release of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span> <span data-ttu-id="b7d45-126">Standardmäßig werden keine Informationen an Microsoft gesendet.</span><span class="sxs-lookup"><span data-stu-id="b7d45-126">By default, no information is sent to Microsoft.</span></span> <span data-ttu-id="b7d45-127">Allerdings beim Kompilieren einer Anwendung mit `-errorreport:queue`, die standardmäßig aktiviert ist, sammelt die Anwendung ihre Fehlerberichte.</span><span class="sxs-lookup"><span data-stu-id="b7d45-127">However, when you compile an application by using `-errorreport:queue`, which is enabled by default, the application collects its error reports.</span></span> <span data-ttu-id="b7d45-128">Klicken Sie dann bei dem Computer anmeldet, zeigt Berichtssystems Fehler ein Popup-Fenster, das ermöglicht dem Administrator die Weiterleitung an Microsoft, die alle Fehler meldet, die seit der Anmeldung aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="b7d45-128">Then, when the computer's administrator logs in, the error reporting system displays a pop-up window that enables the administrator to forward to Microsoft any error reports that occurred since the logon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b7d45-129">Die `/bugreport` Option ist nicht innerhalb der Visual Studio-Entwicklungsumgebung verfügbar, steht er nur, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="b7d45-129">The `/bugreport` option is not available from within the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7d45-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b7d45-130">Example</span></span>  
 <span data-ttu-id="b7d45-131">Im folgende Beispiel kompiliert `T2.vb` und alle Fehlerberichte Informationen in der Datei `Problem.txt`.</span><span class="sxs-lookup"><span data-stu-id="b7d45-131">The following example compiles `T2.vb` and puts all bug-reporting information in the file `Problem.txt`.</span></span>  
  
```  
vbc -bugreport:problem.txt t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="b7d45-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7d45-132">See Also</span></span>  
 [<span data-ttu-id="b7d45-133">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="b7d45-133">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="b7d45-134">-debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b7d45-134">-debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)  
 [<span data-ttu-id="b7d45-135">-errorreport</span><span class="sxs-lookup"><span data-stu-id="b7d45-135">-errorreport</span></span>](../../../visual-basic/reference/command-line-compiler/errorreport.md)  
 [<span data-ttu-id="b7d45-136">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="b7d45-136">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="b7d45-137">TrustLevel Element für SecurityPolicy ((ASP.NET Settings Schema)</span><span class="sxs-lookup"><span data-stu-id="b7d45-137">trustLevel Element for securityPolicy (ASP.NET Settings Schema)</span></span>](http://msdn.microsoft.com/library/729ab04c-03da-4ee5-86b1-be9d08a09369)
