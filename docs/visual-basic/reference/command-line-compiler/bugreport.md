---
title: / bugreport | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b959ef7958cffbbb31f3907eaf8749ca93ac538d
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="bugreport"></a><span data-ttu-id="a06b8-102">/bugreport</span><span class="sxs-lookup"><span data-stu-id="a06b8-102">/bugreport</span></span>
<span data-ttu-id="a06b8-103">Erstellt eine Datei, die Sie verwenden können, wenn Sie einen Fehlerbericht speichern.</span><span class="sxs-lookup"><span data-stu-id="a06b8-103">Creates a file that you can use when you file a bug report.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a06b8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a06b8-104">Syntax</span></span>  
  
```  
/bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="a06b8-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="a06b8-105">Arguments</span></span>  
  
|<span data-ttu-id="a06b8-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="a06b8-106">Term</span></span>|<span data-ttu-id="a06b8-107">Definition</span><span class="sxs-lookup"><span data-stu-id="a06b8-107">Definition</span></span>|  
|---|---|  
|`file`|<span data-ttu-id="a06b8-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a06b8-108">Required.</span></span> <span data-ttu-id="a06b8-109">Der Name der Datei, die den Problembericht enthalten wird.</span><span class="sxs-lookup"><span data-stu-id="a06b8-109">The name of the file that will contain your bug report.</span></span> <span data-ttu-id="a06b8-110">Schließen Sie den Dateinamen in Anführungszeichen (""), wenn der Name ein Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="a06b8-110">Enclose the file name in quotation marks (" ") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a06b8-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a06b8-111">Remarks</span></span>  
 <span data-ttu-id="a06b8-112">Die folgenden Informationen hinzugefügt `file`:</span><span class="sxs-lookup"><span data-stu-id="a06b8-112">The following information is added to `file`:</span></span>  
  
-   <span data-ttu-id="a06b8-113">Eine Kopie der alle Quellcodedateien in der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="a06b8-113">A copy of all source-code files in the compilation.</span></span>  
  
-   <span data-ttu-id="a06b8-114">Eine Liste der Compileroptionen in der Kompilierung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a06b8-114">A list of the compiler options used in the compilation.</span></span>  
  
-   <span data-ttu-id="a06b8-115">Versionsinformationen über den Compiler, gemeinsame Sprachlaufzeit und Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="a06b8-115">Version information about your compiler, common language runtime, and operating system.</span></span>  
  
-   <span data-ttu-id="a06b8-116">Compilerausgabe, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="a06b8-116">Compiler output, if any.</span></span>  
  
-   <span data-ttu-id="a06b8-117">Eine Beschreibung des Problems, für die Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="a06b8-117">A description of the problem, for which you are prompted.</span></span>  
  
-   <span data-ttu-id="a06b8-118">Eine Beschreibung Ihres das Problem Vorschlags sollte behoben werden, für die Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="a06b8-118">A description of how you think the problem should be fixed, for which you are prompted.</span></span>  
  
 <span data-ttu-id="a06b8-119">Da eine Kopie aller Quellcodedateien in enthaltene `file`, Sie möchten den (vermuteten) Codefehler in einem möglichst kurzen Programm zu reproduzieren.</span><span class="sxs-lookup"><span data-stu-id="a06b8-119">Because a copy of all source-code files is included in `file`, you may want to reproduce the (suspected) code defect in the shortest possible program.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a06b8-120">Die `/bugreport` -Option erstellt eine Datei, die möglicherweise vertrauliche Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="a06b8-120">The `/bugreport` option produces a file that contains potentially sensitive information.</span></span> <span data-ttu-id="a06b8-121">Dies schließt die aktuelle Uhrzeit, Compilerversion [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] Version, Betriebssystemversion, Benutzername, die Befehlszeilenargumente, mit denen der Compiler ausgeführt wurde, der gesamte Quellcode und die binäre Form eines referenzierten Assemblys.</span><span class="sxs-lookup"><span data-stu-id="a06b8-121">This includes current time, compiler version, [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] version, OS version, user name, the command-line arguments with which the compiler was run, all source code, and the binary form of any referenced assembly.</span></span> <span data-ttu-id="a06b8-122">Diese Option kann durch Angabe von Befehlszeilenoptionen in der Datei Web.config für eine serverseitige Kompilierung zugegriffen werden eine [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)] Anwendung.</span><span class="sxs-lookup"><span data-stu-id="a06b8-122">This option can be accessed by specifying command-line options in the Web.config file for a server-side compilation of an [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)] application.</span></span> <span data-ttu-id="a06b8-123">Um dies zu verhindern, ändern Sie die Datei Machine.config zum Verweigern von Benutzern auf dem Server zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="a06b8-123">To prevent this, modify the Machine.config file to disallow users from compiling on the server.</span></span>  
  
 <span data-ttu-id="a06b8-124">Wenn diese Option verwendet wird, mit `/errorreport:prompt`, `/errorreport:queue`, oder `/errorreport:send`, und der Anwendung auftritt, einen interner Compilerfehler, die Informationen im `file` an die Microsoft Corporation gesendet.</span><span class="sxs-lookup"><span data-stu-id="a06b8-124">If this option is used with `/errorreport:prompt`, `/errorreport:queue`, or `/errorreport:send`, and your application encounters an internal compiler error, the information in `file` is sent to Microsoft Corporation.</span></span> <span data-ttu-id="a06b8-125">Diese Informationen helfen Microsoft-Technikern, die Ursache des Fehlers zu identifizieren und die nächste Version von zu verbessern [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="a06b8-125">That information will help Microsoft engineers identify the cause of the error and may help improve the next release of [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span> <span data-ttu-id="a06b8-126">Standardmäßig ist keine Informationen an Microsoft gesendet.</span><span class="sxs-lookup"><span data-stu-id="a06b8-126">By default, no information is sent to Microsoft.</span></span> <span data-ttu-id="a06b8-127">Allerdings beim Kompilieren einer Anwendung mit `/errorreport:queue`, die standardmäßig aktiviert ist, sammelt die Anwendung ihre Fehlerberichte.</span><span class="sxs-lookup"><span data-stu-id="a06b8-127">However, when you compile an application by using `/errorreport:queue`, which is enabled by default, the application collects its error reports.</span></span> <span data-ttu-id="a06b8-128">Klicken Sie dann, wenn der Administrator des Computers anmeldet, wird Fehler reporting ein Popup-Fenster, mit der Administratoren zum Weiterleiten an Microsoft Fehler meldet, die seit der Anmeldung aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="a06b8-128">Then, when the computer's administrator logs in, the error reporting system displays a pop-up window that enables the administrator to forward to Microsoft any error reports that occurred since the logon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a06b8-129">Die `/bugreport` Option ist nicht verfügbar in der Visual Studio Development Environment; es kann nur, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="a06b8-129">The `/bugreport` option is not available from within the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a06b8-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a06b8-130">Example</span></span>  
 <span data-ttu-id="a06b8-131">Das folgende Beispiel kompiliert `T2.vb` und alle Informationen in der Datei `Problem.txt`.</span><span class="sxs-lookup"><span data-stu-id="a06b8-131">The following example compiles `T2.vb` and puts all bug-reporting information in the file `Problem.txt`.</span></span>  
  
```  
vbc /bugreport:problem.txt t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="a06b8-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a06b8-132">See Also</span></span>  
 <span data-ttu-id="a06b8-133">[Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="a06b8-133">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="a06b8-134"> [/ Debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md) </span><span class="sxs-lookup"><span data-stu-id="a06b8-134"> [/debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md) </span></span>  
<span data-ttu-id="a06b8-135"> [/ errorreport](../../../visual-basic/reference/command-line-compiler/errorreport.md) </span><span class="sxs-lookup"><span data-stu-id="a06b8-135"> [/errorreport](../../../visual-basic/reference/command-line-compiler/errorreport.md) </span></span>  
<span data-ttu-id="a06b8-136"> [Beispiel für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="a06b8-136"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="a06b8-137"> [TrustLevel-Element für SecurityPolicy ((ASP.NET Settings Schema)](http://msdn.microsoft.com/en-us/729ab04c-03da-4ee5-86b1-be9d08a09369)</span><span class="sxs-lookup"><span data-stu-id="a06b8-137"> [trustLevel Element for securityPolicy (ASP.NET Settings Schema)](http://msdn.microsoft.com/en-us/729ab04c-03da-4ee5-86b1-be9d08a09369)</span></span>
