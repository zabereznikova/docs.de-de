---
title: -bugreport
ms.date: 03/08/2018
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
ms.openlocfilehash: 4b468b8ee4301693312e9545396f2b9f495f75d8
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90550910"
---
# <a name="-bugreport"></a><span data-ttu-id="4d5ef-102">-bugreport</span><span class="sxs-lookup"><span data-stu-id="4d5ef-102">-bugreport</span></span>

<span data-ttu-id="4d5ef-103">Hiermit wird eine Datei erstellt, die Sie verwenden können, wenn Sie einen Fehlerbericht übermitteln.</span><span class="sxs-lookup"><span data-stu-id="4d5ef-103">Creates a file that you can use when you file a bug report.</span></span>

## <a name="syntax"></a><span data-ttu-id="4d5ef-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4d5ef-104">Syntax</span></span>

```console
-bugreport:file
```

## <a name="arguments"></a><span data-ttu-id="4d5ef-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="4d5ef-105">Arguments</span></span>

|<span data-ttu-id="4d5ef-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="4d5ef-106">Term</span></span>|<span data-ttu-id="4d5ef-107">Definition</span><span class="sxs-lookup"><span data-stu-id="4d5ef-107">Definition</span></span>|
|---|---|
|`file`|<span data-ttu-id="4d5ef-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4d5ef-108">Required.</span></span> <span data-ttu-id="4d5ef-109">Dies ist der Name der Datei, die Ihren Fehlerbericht enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="4d5ef-109">The name of the file that will contain your bug report.</span></span> <span data-ttu-id="4d5ef-110">Wenn der Name ein Leerzeichen enthält, müssen Sie den Dateinamen in Anführungszeichen einschließen (" ").</span><span class="sxs-lookup"><span data-stu-id="4d5ef-110">Enclose the file name in quotation marks (" ") if the name contains a space.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4d5ef-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4d5ef-111">Remarks</span></span>

<span data-ttu-id="4d5ef-112">Die folgenden Informationen werden `file` hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="4d5ef-112">The following information is added to `file`:</span></span>

- <span data-ttu-id="4d5ef-113">Kopie aller Quellcodedateien in der Kompilierung</span><span class="sxs-lookup"><span data-stu-id="4d5ef-113">A copy of all source-code files in the compilation.</span></span>

- <span data-ttu-id="4d5ef-114">Liste der bei der Kompilierung verwendeten Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="4d5ef-114">A list of the compiler options used in the compilation.</span></span>

- <span data-ttu-id="4d5ef-115">Versionsinformationen über den Compiler, die Common Language Runtime und das Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="4d5ef-115">Version information about your compiler, common language runtime, and operating system.</span></span>

- <span data-ttu-id="4d5ef-116">Compilerausgabe, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="4d5ef-116">Compiler output, if any.</span></span>

- <span data-ttu-id="4d5ef-117">Beschreibung des gemeldeten Problems</span><span class="sxs-lookup"><span data-stu-id="4d5ef-117">A description of the problem, for which you are prompted.</span></span>

- <span data-ttu-id="4d5ef-118">Beschreibung Ihres Vorschlags zur Beseitigung des gemeldeten Problems</span><span class="sxs-lookup"><span data-stu-id="4d5ef-118">A description of how you think the problem should be fixed, for which you are prompted.</span></span>

<span data-ttu-id="4d5ef-119">Da in `file` Kopien von allen Quellcodedateien enthalten sind, sollten Sie den (vermuteten) Codefehler im möglichst kürzesten Programm reproduzieren.</span><span class="sxs-lookup"><span data-stu-id="4d5ef-119">Because a copy of all source-code files is included in `file`, you may want to reproduce the (suspected) code defect in the shortest possible program.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4d5ef-120">Mit der Option `-bugreport` wird eine Datei erstellt, die potenziell vertrauliche Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="4d5ef-120">The `-bugreport` option produces a file that contains potentially sensitive information.</span></span> <span data-ttu-id="4d5ef-121">Dies umfasst die aktuelle Uhrzeit, Compilerversion, .NET Framework-Version, Betriebssystemversion, den Benutzernamen, die Befehlszeilenargumente zum Ausführen des Compilers, den gesamten Quellcode und die binäre Form einer Assembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="4d5ef-121">This includes current time, compiler version, .NET Framework version, OS version, user name, the command-line arguments with which the compiler was run, all source code, and the binary form of any referenced assembly.</span></span> <span data-ttu-id="4d5ef-122">Auf diese Option können Sie zugreifen, indem Sie in der Web.config-Datei Befehlszeilenoptionen für eine serverseitige Kompilierung einer ASP.NET-Anwendung angeben.</span><span class="sxs-lookup"><span data-stu-id="4d5ef-122">This option can be accessed by specifying command-line options in the Web.config file for a server-side compilation of an ASP.NET application.</span></span> <span data-ttu-id="4d5ef-123">Ändern Sie die Machine.config-Datei, um Benutzern das Kompilieren auf dem Server zu verbieten und dies zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="4d5ef-123">To prevent this, modify the Machine.config file to disallow users from compiling on the server.</span></span>

<span data-ttu-id="4d5ef-124">Wenn diese Option mit `-errorreport:prompt`, `-errorreport:queue` oder `-errorreport:send` verwendet wird und die Anwendung einen internen Compilerfehler findet, werden die Informationen in `file` an die Microsoft Corporation gesendet.</span><span class="sxs-lookup"><span data-stu-id="4d5ef-124">If this option is used with `-errorreport:prompt`, `-errorreport:queue`, or `-errorreport:send`, and your application encounters an internal compiler error, the information in `file` is sent to Microsoft Corporation.</span></span> <span data-ttu-id="4d5ef-125">Diese Informationen helfen Microsoft-Entwicklern dabei, die Ursache des Fehlers zu ermitteln und die nächste Version von Visual Basic zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="4d5ef-125">That information will help Microsoft engineers identify the cause of the error and may help improve the next release of Visual Basic.</span></span> <span data-ttu-id="4d5ef-126">Standardmäßig werden keine Informationen an Microsoft gesendet.</span><span class="sxs-lookup"><span data-stu-id="4d5ef-126">By default, no information is sent to Microsoft.</span></span> <span data-ttu-id="4d5ef-127">Wenn Sie jedoch eine Anwendung mit `-errorreport:queue` kompilieren, die standardmäßig aktiviert ist, sammelt die Anwendung die Fehlerberichte.</span><span class="sxs-lookup"><span data-stu-id="4d5ef-127">However, when you compile an application by using `-errorreport:queue`, which is enabled by default, the application collects its error reports.</span></span> <span data-ttu-id="4d5ef-128">Wenn sich der Administrator des Computers dann anmeldet, zeigt das Fehlermeldungssystem ein Popupfenster an, mit dem der Administrator alle Fehlerberichte, die seit der Anmeldung aufgetreten sind, an Microsoft weiterleiten kann.</span><span class="sxs-lookup"><span data-stu-id="4d5ef-128">Then, when the computer's administrator logs in, the error reporting system displays a pop-up window that enables the administrator to forward to Microsoft any error reports that occurred since the logon.</span></span>

> [!NOTE]
> <span data-ttu-id="4d5ef-129">Die Option `-bugreport` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="4d5ef-129">The `-bugreport` option is not available from within the Visual Studio development environment; it is available only when you compile from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="4d5ef-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4d5ef-130">Example</span></span>

<span data-ttu-id="4d5ef-131">Im folgenden Beispiel wird *T2.vb* kompiliert, und alle Fehlerberichtinformationen werden in die Datei *Problem.txt* eingefügt.</span><span class="sxs-lookup"><span data-stu-id="4d5ef-131">The following example compiles *T2.vb* and puts all bug-reporting information in the file *Problem.txt*.</span></span>

```console
vbc -bugreport:problem.txt t2.vb
```

## <a name="see-also"></a><span data-ttu-id="4d5ef-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d5ef-132">See also</span></span>

- [<span data-ttu-id="4d5ef-133">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="4d5ef-133">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="4d5ef-134">-debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4d5ef-134">-debug (Visual Basic)</span></span>](debug.md)
- [<span data-ttu-id="4d5ef-135">-errorreport</span><span class="sxs-lookup"><span data-stu-id="4d5ef-135">-errorreport</span></span>](errorreport.md)
- [<span data-ttu-id="4d5ef-136">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="4d5ef-136">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- <span data-ttu-id="4d5ef-137">[trustLevel-Element für securityPolicy (ASP.NET-Einstellungsschema)](/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="4d5ef-137">[trustLevel Element for securityPolicy (ASP.NET Settings Schema)](/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span></span>
