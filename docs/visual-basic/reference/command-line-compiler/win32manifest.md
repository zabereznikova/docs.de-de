---
title: -win32manifest
ms.date: 03/13/2018
helpviewer_keywords:
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
ms.openlocfilehash: cef1e6c19e7fdd6fc9f42c8fc36008314ea80a80
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349128"
---
# <a name="-win32manifest-visual-basic"></a><span data-ttu-id="3cc5d-102">-win32manifest (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3cc5d-102">-win32manifest (Visual Basic)</span></span>
<span data-ttu-id="3cc5d-103">Identifiziert eine benutzerdefinierte Win32-Anwendungsmanifestdatei, die in die übertragbare ausführbare Datei (PE) eines Projekts eingebettet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3cc5d-103">Identifies a user-defined Win32 application manifest file to be embedded into a project's portable executable (PE) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cc5d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3cc5d-104">Syntax</span></span>  
  
```console  
-win32manifest: fileName  
```  
  
## <a name="arguments"></a><span data-ttu-id="3cc5d-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="3cc5d-105">Arguments</span></span>  
  
|<span data-ttu-id="3cc5d-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="3cc5d-106">Term</span></span>|<span data-ttu-id="3cc5d-107">Definition</span><span class="sxs-lookup"><span data-stu-id="3cc5d-107">Definition</span></span>|  
|---|---|  
|`fileName`|<span data-ttu-id="3cc5d-108">Pfad der benutzerdefinierten Manifestdatei.</span><span class="sxs-lookup"><span data-stu-id="3cc5d-108">The path of the custom manifest file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3cc5d-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3cc5d-109">Remarks</span></span>  
 <span data-ttu-id="3cc5d-110">Standardmäßig bettet der Visual Basic-Compiler ein Anwendungsmanifest ein, das eine angeforderte Ausführungsebene als „asInvoker“ angibt.</span><span class="sxs-lookup"><span data-stu-id="3cc5d-110">By default, the Visual Basic compiler embeds an application manifest that specifies a requested execution level of asInvoker.</span></span> <span data-ttu-id="3cc5d-111">Er erstellt das Manifest in demselben Ordner, in dem die ausführbare Datei erstellt wird. Wenn Sie Visual Studio verwenden, ist dies in der Regel der Ordner „bin\Debug“ oder „bin\Release“.</span><span class="sxs-lookup"><span data-stu-id="3cc5d-111">It creates the manifest in the same folder in which the executable file is built, typically the bin\Debug or bin\Release folder when you use Visual Studio.</span></span> <span data-ttu-id="3cc5d-112">Wenn Sie ein benutzerdefiniertes Manifest bereitstellen möchten, z. B. um die angeforderte Ausführungsebene „highestAvailable“ oder „requireAdministrator“ anzugeben, verwenden Sie diese Option zur Angabe des Dateinamens.</span><span class="sxs-lookup"><span data-stu-id="3cc5d-112">If you want to supply a custom manifest, for example to specify a requested execution level of highestAvailable or requireAdministrator, use this option to specify the name of the file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3cc5d-113">Diese Option und die Option [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) schließen sich gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="3cc5d-113">This option and the [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) option are mutually exclusive.</span></span> <span data-ttu-id="3cc5d-114">Wenn Sie versuchen, beide Optionen in derselben Befehlszeile zu verwenden, wird ein Buildfehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3cc5d-114">If you try to use both options in the same command line, you will get a build error.</span></span>  
  
 <span data-ttu-id="3cc5d-115">Eine Anwendung ohne Anwendungsmanifest, das eine angeforderte Anwendungsebene angibt, unterliegt der Datei- und Registrierungsvirtualisierung unter der Benutzerkontensteuerung in Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="3cc5d-115">An application that has no application manifest that specifies a requested execution level will be subject to file/registry virtualization under the User Account Control feature in Windows Vista.</span></span> <span data-ttu-id="3cc5d-116">Weitere Informationen über Virtualisierung finden Sie unter [ClickOnce-Bereitstellung unter Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span><span class="sxs-lookup"><span data-stu-id="3cc5d-116">For more information about virtualization, see [ClickOnce Deployment on Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span></span>  
  
 <span data-ttu-id="3cc5d-117">Die Anwendung unterliegt der Virtualisierung, wenn eine der folgenden Bedingungen erfüllt ist:</span><span class="sxs-lookup"><span data-stu-id="3cc5d-117">Your application will be subject to virtualization if either of the following conditions is true:</span></span>  
  
1. <span data-ttu-id="3cc5d-118">Sie verwenden die Option `-nowin32manifest` und stellen in einem späteren Buildschritt oder als Teil einer Windows-Ressourcendatei (RES-Datei) kein Manifest bereit, indem Sie die Option `-win32resource` verwenden.</span><span class="sxs-lookup"><span data-stu-id="3cc5d-118">You use the `-nowin32manifest` option and you do not provide a manifest in a later build step or as part of a Windows Resource (.res) file by using the `-win32resource` option.</span></span>  
  
2. <span data-ttu-id="3cc5d-119">Sie stellen ein benutzerdefiniertes Manifest bereit, das keine angeforderte Ausführungsebene angibt.</span><span class="sxs-lookup"><span data-stu-id="3cc5d-119">You provide a custom manifest that does not specify a requested execution level.</span></span>  
  
 <span data-ttu-id="3cc5d-120">Visual Studio erstellt eine MANIFEST-Standarddatei und speichert sie zusammen mit der ausführbaren Datei in den Debug- oder Releaseverzeichnissen.</span><span class="sxs-lookup"><span data-stu-id="3cc5d-120">Visual Studio creates a default .manifest file and stores it in the debug and release directories alongside the executable file.</span></span> <span data-ttu-id="3cc5d-121">Klicken Sie zum Anzeigen oder Bearbeiten der „app.manifest“-Standarddatei im Projekt-Designer auf der Registerkarte **Anwendung** auf **UAC-Einstellungen anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="3cc5d-121">You can view or edit the default app.manifest file by clicking **View UAC Settings** on the **Application** tab in the Project Designer.</span></span> <span data-ttu-id="3cc5d-122">Weitere Informationen finden Sie unter [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="3cc5d-122">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="3cc5d-123">Sie können das Anwendungsmanifest als benutzerdefinierten Postbuildschritt oder als Teil einer Win32-Ressourcendatei bereitstellen, indem Sie die Option `-nowin32manifest` verwenden.</span><span class="sxs-lookup"><span data-stu-id="3cc5d-123">You can provide the application manifest as a custom post-build step or as part of a Win32 resource file by using the `-nowin32manifest` option.</span></span> <span data-ttu-id="3cc5d-124">Verwenden Sie dieselbe Option, wenn Ihre Anwendung der Datei- oder Registrierungsvirtualisierung unter Windows Vista unterliegen soll.</span><span class="sxs-lookup"><span data-stu-id="3cc5d-124">Use that same option if you want your application to be subject to file or registry virtualization on Windows Vista.</span></span> <span data-ttu-id="3cc5d-125">Dadurch wird verhindert, dass der Compiler ein Standardmanifest in der PE-Datei erstellt und einbettet.</span><span class="sxs-lookup"><span data-stu-id="3cc5d-125">This will prevent the compiler from creating and embedding a default manifest in the PE file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3cc5d-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3cc5d-126">Example</span></span>  
 <span data-ttu-id="3cc5d-127">Das folgende Beispiel zeigt das Standardmanifest, das der Visual Basic-Compiler in eine PE-Datei einfügt.</span><span class="sxs-lookup"><span data-stu-id="3cc5d-127">The following example shows the default manifest that the Visual Basic compiler inserts into a PE.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3cc5d-128">Der Compiler fügt einen Standardanwendungsnamen („MyApplication.app“) in die XML-Manifestdatei ein.</span><span class="sxs-lookup"><span data-stu-id="3cc5d-128">The compiler inserts a standard application name MyApplication.app into the manifest XML.</span></span> <span data-ttu-id="3cc5d-129">Mit dieser Problemumgehung können Anwendungen unter Windows Server 2003 Service Pack 3 ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3cc5d-129">This is a workaround to enable applications to run on Windows Server 2003 Service Pack 3.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
  <assemblyIdentity version="1.0.0.0" name="MyApplication.app"/>  
  <trustInfo xmlns="urn:schemas-microsoft-com:asm.v2">  
    <security>  
      <requestedPrivileges xmlns="urn:schemas-microsoft-com:asm.v3">  
        <requestedExecutionLevel level="asInvoker"/>  
      </requestedPrivileges>  
    </security>  
  </trustInfo>  
</assembly>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3cc5d-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3cc5d-130">See also</span></span>

- [<span data-ttu-id="3cc5d-131">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="3cc5d-131">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="3cc5d-132">-nowin32manifest (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3cc5d-132">-nowin32manifest (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)
