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
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349128"
---
# <a name="-win32manifest-visual-basic"></a><span data-ttu-id="52dfc-102">-win32manifest (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="52dfc-102">-win32manifest (Visual Basic)</span></span>
<span data-ttu-id="52dfc-103">Identifiziert eine benutzerdefinierte Win32-Anwendungsmanifestdatei, die in die übertragbare ausführbare Datei (PE) eines Projekts eingebettet werden soll.</span><span class="sxs-lookup"><span data-stu-id="52dfc-103">Identifies a user-defined Win32 application manifest file to be embedded into a project's portable executable (PE) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52dfc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="52dfc-104">Syntax</span></span>  
  
```console  
-win32manifest: fileName  
```  
  
## <a name="arguments"></a><span data-ttu-id="52dfc-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="52dfc-105">Arguments</span></span>  
  
|<span data-ttu-id="52dfc-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="52dfc-106">Term</span></span>|<span data-ttu-id="52dfc-107">Definition</span><span class="sxs-lookup"><span data-stu-id="52dfc-107">Definition</span></span>|  
|---|---|  
|`fileName`|<span data-ttu-id="52dfc-108">Der Pfad der benutzerdefinierten Manifest-Datei.</span><span class="sxs-lookup"><span data-stu-id="52dfc-108">The path of the custom manifest file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52dfc-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="52dfc-109">Remarks</span></span>  
 <span data-ttu-id="52dfc-110">Standardmäßig bettet der Visual Basic-Compiler ein Anwendungs Manifest ein, das die angeforderte Ausführungs Ebene "asInvoker" angibt.</span><span class="sxs-lookup"><span data-stu-id="52dfc-110">By default, the Visual Basic compiler embeds an application manifest that specifies a requested execution level of asInvoker.</span></span> <span data-ttu-id="52dfc-111">Er erstellt das Manifest im selben Ordner, in dem die ausführbare Datei erstellt wird. in der Regel ist dies der Ordner "bin\debug" oder "Bin\Release", wenn Sie Visual Studio verwenden.</span><span class="sxs-lookup"><span data-stu-id="52dfc-111">It creates the manifest in the same folder in which the executable file is built, typically the bin\Debug or bin\Release folder when you use Visual Studio.</span></span> <span data-ttu-id="52dfc-112">Wenn Sie ein benutzerdefiniertes Manifest angeben möchten, z. b. um die angeforderte Ausführungs Ebene "highestAvailable" oder "requiinfoministrator" anzugeben, verwenden Sie diese Option, um den Namen der Datei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="52dfc-112">If you want to supply a custom manifest, for example to specify a requested execution level of highestAvailable or requireAdministrator, use this option to specify the name of the file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="52dfc-113">Diese Option und die Option " [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) " schließen sich gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="52dfc-113">This option and the [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) option are mutually exclusive.</span></span> <span data-ttu-id="52dfc-114">Wenn Sie versuchen, beide Optionen in derselben Befehlszeile zu verwenden, erhalten Sie einen Buildfehler.</span><span class="sxs-lookup"><span data-stu-id="52dfc-114">If you try to use both options in the same command line, you will get a build error.</span></span>  
  
 <span data-ttu-id="52dfc-115">Eine Anwendung ohne Anwendungsmanifest, das eine angeforderte Anwendungsebene angibt, unterliegt der Datei- und Registrierungsvirtualisierung unter der Benutzerkontensteuerung in Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="52dfc-115">An application that has no application manifest that specifies a requested execution level will be subject to file/registry virtualization under the User Account Control feature in Windows Vista.</span></span> <span data-ttu-id="52dfc-116">Weitere Informationen über Virtualisierung finden Sie unter [ClickOnce-Bereitstellung unter Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span><span class="sxs-lookup"><span data-stu-id="52dfc-116">For more information about virtualization, see [ClickOnce Deployment on Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span></span>  
  
 <span data-ttu-id="52dfc-117">Die Anwendung unterliegt der Virtualisierung, wenn eine der folgenden Bedingungen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="52dfc-117">Your application will be subject to virtualization if either of the following conditions is true:</span></span>  
  
1. <span data-ttu-id="52dfc-118">Mithilfe der Option `-nowin32manifest` können Sie in einem späteren Buildschritt oder als Teil einer Windows-Ressourcen Datei (. res) kein Manifest bereitstellen, indem Sie die `-win32resource`-Option verwenden.</span><span class="sxs-lookup"><span data-stu-id="52dfc-118">You use the `-nowin32manifest` option and you do not provide a manifest in a later build step or as part of a Windows Resource (.res) file by using the `-win32resource` option.</span></span>  
  
2. <span data-ttu-id="52dfc-119">Sie stellen ein benutzerdefiniertes Manifest bereit, das keine angeforderte Ausführungsebene angibt.</span><span class="sxs-lookup"><span data-stu-id="52dfc-119">You provide a custom manifest that does not specify a requested execution level.</span></span>  
  
 <span data-ttu-id="52dfc-120">Visual Studio erstellt eine MANIFEST-Standarddatei und speichert sie zusammen mit der ausführbaren Datei in den Debug- oder Releaseverzeichnissen.</span><span class="sxs-lookup"><span data-stu-id="52dfc-120">Visual Studio creates a default .manifest file and stores it in the debug and release directories alongside the executable file.</span></span> <span data-ttu-id="52dfc-121">Sie können die Standarddatei "App. Manifest" anzeigen oder bearbeiten, indem Sie im Projekt-Designer auf der Registerkarte **Anwendung** auf **UAC-Einstellungen anzeigen** klicken.</span><span class="sxs-lookup"><span data-stu-id="52dfc-121">You can view or edit the default app.manifest file by clicking **View UAC Settings** on the **Application** tab in the Project Designer.</span></span> <span data-ttu-id="52dfc-122">Weitere Informationen finden Sie unter [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="52dfc-122">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="52dfc-123">Sie können das Anwendungs Manifest mithilfe der Option `-nowin32manifest` als benutzerdefinierten Postbuildschritt oder als Teil einer Win32-Ressourcen Datei bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="52dfc-123">You can provide the application manifest as a custom post-build step or as part of a Win32 resource file by using the `-nowin32manifest` option.</span></span> <span data-ttu-id="52dfc-124">Verwenden Sie dieselbe Option, wenn Ihre Anwendung der Datei- oder Registrierungsvirtualisierung unter Windows Vista unterliegen soll.</span><span class="sxs-lookup"><span data-stu-id="52dfc-124">Use that same option if you want your application to be subject to file or registry virtualization on Windows Vista.</span></span> <span data-ttu-id="52dfc-125">Dadurch wird verhindert, dass der Compiler ein Standard Manifest in die PE-Datei erstellt und einbettet.</span><span class="sxs-lookup"><span data-stu-id="52dfc-125">This will prevent the compiler from creating and embedding a default manifest in the PE file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52dfc-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="52dfc-126">Example</span></span>  
 <span data-ttu-id="52dfc-127">Das folgende Beispiel zeigt das Standard Manifest, das der Visual Basic Compiler in ein PE einfügt.</span><span class="sxs-lookup"><span data-stu-id="52dfc-127">The following example shows the default manifest that the Visual Basic compiler inserts into a PE.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="52dfc-128">Der Compiler fügt den Standard Anwendungsnamen MyApplication. app in das Manifest-XML ein.</span><span class="sxs-lookup"><span data-stu-id="52dfc-128">The compiler inserts a standard application name MyApplication.app into the manifest XML.</span></span> <span data-ttu-id="52dfc-129">Mit dieser Problemumgehung können Anwendungen unter Windows Server 2003 Service Pack 3 ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="52dfc-129">This is a workaround to enable applications to run on Windows Server 2003 Service Pack 3.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="52dfc-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="52dfc-130">See also</span></span>

- [<span data-ttu-id="52dfc-131">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="52dfc-131">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="52dfc-132">-nowin32manifest (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="52dfc-132">-nowin32manifest (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)
