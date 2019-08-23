---
title: -bugreport
ms.date: 03/08/2018
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
ms.openlocfilehash: 75c3e5842447a8f0812d5a90d7157f7a6a496936
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962446"
---
# <a name="-bugreport"></a><span data-ttu-id="a5984-102">-bugreport</span><span class="sxs-lookup"><span data-stu-id="a5984-102">-bugreport</span></span>
<span data-ttu-id="a5984-103">Erstellt eine Datei, die Sie verwenden können, wenn Sie einen Fehlerbericht melden.</span><span class="sxs-lookup"><span data-stu-id="a5984-103">Creates a file that you can use when you file a bug report.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5984-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a5984-104">Syntax</span></span>  
  
```  
-bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="a5984-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="a5984-105">Arguments</span></span>  
  
|<span data-ttu-id="a5984-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="a5984-106">Term</span></span>|<span data-ttu-id="a5984-107">Definition</span><span class="sxs-lookup"><span data-stu-id="a5984-107">Definition</span></span>|  
|---|---|  
|`file`|<span data-ttu-id="a5984-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a5984-108">Required.</span></span> <span data-ttu-id="a5984-109">Der Name der Datei, in der der Fehlerbericht enthalten sein soll.</span><span class="sxs-lookup"><span data-stu-id="a5984-109">The name of the file that will contain your bug report.</span></span> <span data-ttu-id="a5984-110">Schließen Sie den Dateinamen in Anführungszeichen ("") ein, wenn der Name ein Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="a5984-110">Enclose the file name in quotation marks (" ") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5984-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a5984-111">Remarks</span></span>  
 <span data-ttu-id="a5984-112">Folgende Informationen werden hinzugefügt `file`:</span><span class="sxs-lookup"><span data-stu-id="a5984-112">The following information is added to `file`:</span></span>  
  
- <span data-ttu-id="a5984-113">Eine Kopie aller Quell Code Dateien in der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="a5984-113">A copy of all source-code files in the compilation.</span></span>  
  
- <span data-ttu-id="a5984-114">Eine Liste der Compileroptionen, die in der Kompilierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a5984-114">A list of the compiler options used in the compilation.</span></span>  
  
- <span data-ttu-id="a5984-115">Versionsinformationen über den Compiler, Common Language Runtime und das Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="a5984-115">Version information about your compiler, common language runtime, and operating system.</span></span>  
  
- <span data-ttu-id="a5984-116">Compilerausgabe, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="a5984-116">Compiler output, if any.</span></span>  
  
- <span data-ttu-id="a5984-117">Eine Beschreibung des Problems, für das Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="a5984-117">A description of the problem, for which you are prompted.</span></span>  
  
- <span data-ttu-id="a5984-118">Eine Beschreibung, wie Sie der Ansicht sind, dass das Problem behoben werden sollte, für das Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="a5984-118">A description of how you think the problem should be fixed, for which you are prompted.</span></span>  
  
 <span data-ttu-id="a5984-119">Da eine Kopie aller Quell Code Dateien in `file`enthalten ist, kann es ratsam sein, den (verdächtigen) Code Fehler in dem kürzesten Programm zu reproduzieren.</span><span class="sxs-lookup"><span data-stu-id="a5984-119">Because a copy of all source-code files is included in `file`, you may want to reproduce the (suspected) code defect in the shortest possible program.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a5984-120">Mit `-bugreport` der-Option wird eine Datei erstellt, die potenziell vertrauliche Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="a5984-120">The `-bugreport` option produces a file that contains potentially sensitive information.</span></span> <span data-ttu-id="a5984-121">Dies umfasst die aktuelle Uhrzeit, die Compilerversion, .NET Framework Version, die Betriebssystemversion, den Benutzernamen, die Befehlszeilenargumente, mit denen der Compiler ausgeführt wurde, den gesamten Quellcode und die binäre Form einer Assembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="a5984-121">This includes current time, compiler version, .NET Framework version, OS version, user name, the command-line arguments with which the compiler was run, all source code, and the binary form of any referenced assembly.</span></span> <span data-ttu-id="a5984-122">Auf diese Option können Sie zugreifen, indem Sie in der Datei Web. config Befehlszeilenoptionen für eine serverseitige Kompilierung einer ASP.NET-Anwendung angeben.</span><span class="sxs-lookup"><span data-stu-id="a5984-122">This option can be accessed by specifying command-line options in the Web.config file for a server-side compilation of an ASP.NET application.</span></span> <span data-ttu-id="a5984-123">Um dies zu verhindern, ändern Sie die Datei "Machine. config" so, dass Benutzer nicht auf dem Server kompiliert werden können.</span><span class="sxs-lookup"><span data-stu-id="a5984-123">To prevent this, modify the Machine.config file to disallow users from compiling on the server.</span></span>  
  
 <span data-ttu-id="a5984-124">Wenn diese Option `-errorreport:prompt`mit, `-errorreport:queue`oder `-errorreport:send`verwendet wird und die Anwendung auf einen internen Compilerfehler stößt, werden die Informationen `file` in an die Microsoft Corporation gesendet.</span><span class="sxs-lookup"><span data-stu-id="a5984-124">If this option is used with `-errorreport:prompt`, `-errorreport:queue`, or `-errorreport:send`, and your application encounters an internal compiler error, the information in `file` is sent to Microsoft Corporation.</span></span> <span data-ttu-id="a5984-125">Diese Informationen helfen Microsoft-Technikern dabei, die Ursache des Fehlers zu ermitteln, und können die nächste Version von Visual Basic verbessern.</span><span class="sxs-lookup"><span data-stu-id="a5984-125">That information will help Microsoft engineers identify the cause of the error and may help improve the next release of Visual Basic.</span></span> <span data-ttu-id="a5984-126">Standardmäßig werden keine Informationen an Microsoft gesendet.</span><span class="sxs-lookup"><span data-stu-id="a5984-126">By default, no information is sent to Microsoft.</span></span> <span data-ttu-id="a5984-127">Wenn Sie jedoch eine Anwendung mithilfe `-errorreport:queue`von kompilieren, die standardmäßig aktiviert ist, sammelt die Anwendung Ihre Fehlerberichte.</span><span class="sxs-lookup"><span data-stu-id="a5984-127">However, when you compile an application by using `-errorreport:queue`, which is enabled by default, the application collects its error reports.</span></span> <span data-ttu-id="a5984-128">Wenn sich der Administrator des Computers anmeldet, zeigt das Fehler Berichterstattungs System ein Popup Fenster an, mit dem der Administrator alle Fehlerberichte, die seit der Anmeldung aufgetreten sind, an Microsoft weiterleiten kann.</span><span class="sxs-lookup"><span data-stu-id="a5984-128">Then, when the computer's administrator logs in, the error reporting system displays a pop-up window that enables the administrator to forward to Microsoft any error reports that occurred since the logon.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a5984-129">Die `/bugreport` Option ist in der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="a5984-129">The `/bugreport` option is not available from within the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5984-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a5984-130">Example</span></span>  
 <span data-ttu-id="a5984-131">Im folgenden Beispiel werden alle `T2.vb` Fehler Berichterstattungs Informationen kompiliert und in die Datei `Problem.txt`eingefügt.</span><span class="sxs-lookup"><span data-stu-id="a5984-131">The following example compiles `T2.vb` and puts all bug-reporting information in the file `Problem.txt`.</span></span>  
  
```  
vbc -bugreport:problem.txt t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="a5984-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5984-132">See also</span></span>

- [<span data-ttu-id="a5984-133">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="a5984-133">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="a5984-134">-Debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a5984-134">-debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)
- [<span data-ttu-id="a5984-135">-errorreport</span><span class="sxs-lookup"><span data-stu-id="a5984-135">-errorreport</span></span>](../../../visual-basic/reference/command-line-compiler/errorreport.md)
- [<span data-ttu-id="a5984-136">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="a5984-136">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- <span data-ttu-id="a5984-137">[Trust Level-Element für securityPolicy (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a5984-137">[trustLevel Element for securityPolicy (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span></span>
