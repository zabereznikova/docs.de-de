---
title: -win32manifest (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
ms.openlocfilehash: 15fe62457ed11ffcd08a1db3aa8be57080f22869
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59300797"
---
# <a name="-win32manifest-visual-basic"></a><span data-ttu-id="b2f2e-102">-win32manifest (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b2f2e-102">-win32manifest (Visual Basic)</span></span>
<span data-ttu-id="b2f2e-103">Identifiziert eine benutzerdefinierte Win32-Anwendungsmanifestdatei, die in die übertragbare ausführbare Datei (PE) eines Projekts eingebettet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b2f2e-103">Identifies a user-defined Win32 application manifest file to be embedded into a project's portable executable (PE) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2f2e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b2f2e-104">Syntax</span></span>  
  
```  
-win32manifest: fileName  
```  
  
## <a name="arguments"></a><span data-ttu-id="b2f2e-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="b2f2e-105">Arguments</span></span>  
  
|<span data-ttu-id="b2f2e-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="b2f2e-106">Term</span></span>|<span data-ttu-id="b2f2e-107">Definition</span><span class="sxs-lookup"><span data-stu-id="b2f2e-107">Definition</span></span>|  
|---|---|  
|`fileName`|<span data-ttu-id="b2f2e-108">Der Pfad der benutzerdefinierten Manifestdatei.</span><span class="sxs-lookup"><span data-stu-id="b2f2e-108">The path of the custom manifest file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2f2e-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b2f2e-109">Remarks</span></span>  
 <span data-ttu-id="b2f2e-110">Standardmäßig bettet der Visual Basic-Compiler ein Anwendungsmanifest, das eine angeforderte Ausführungsebene "asInvoker" angibt.</span><span class="sxs-lookup"><span data-stu-id="b2f2e-110">By default, the Visual Basic compiler embeds an application manifest that specifies a requested execution level of asInvoker.</span></span> <span data-ttu-id="b2f2e-111">Das Manifest erstellt in demselben Ordner, in dem die ausführbare Datei wird erstellt, in der Regel den Ordner "bin\Debug" oder "bin\Release", bei der Verwendung von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b2f2e-111">It creates the manifest in the same folder in which the executable file is built, typically the bin\Debug or bin\Release folder when you use Visual Studio.</span></span> <span data-ttu-id="b2f2e-112">Wenn Sie ein benutzerdefiniertes Manifest, z. B. zum Festlegen von einer angeforderten Ausführungsebene "highestAvailable" oder "requireAdministrator", angeben möchten verwenden Sie diese Option, um den Namen der Datei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b2f2e-112">If you want to supply a custom manifest, for example to specify a requested execution level of highestAvailable or requireAdministrator, use this option to specify the name of the file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b2f2e-113">Diese Option und die [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) Option schließen sich gegenseitig.</span><span class="sxs-lookup"><span data-stu-id="b2f2e-113">This option and the [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) option are mutually exclusive.</span></span> <span data-ttu-id="b2f2e-114">Wenn Sie versuchen, beide Optionen in der gleichen Befehlszeile verwenden, erhalten Sie einen Buildfehler.</span><span class="sxs-lookup"><span data-stu-id="b2f2e-114">If you try to use both options in the same command line, you will get a build error.</span></span>  
  
 <span data-ttu-id="b2f2e-115">Eine Anwendung ohne Anwendungsmanifest, das eine angeforderte Anwendungsebene angibt, unterliegt der Datei- und Registrierungsvirtualisierung unter der Benutzerkontensteuerung in Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="b2f2e-115">An application that has no application manifest that specifies a requested execution level will be subject to file/registry virtualization under the User Account Control feature in Windows Vista.</span></span> <span data-ttu-id="b2f2e-116">Weitere Informationen über Virtualisierung finden Sie unter [ClickOnce-Bereitstellung unter Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span><span class="sxs-lookup"><span data-stu-id="b2f2e-116">For more information about virtualization, see [ClickOnce Deployment on Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span></span>  
  
 <span data-ttu-id="b2f2e-117">Ihre Anwendung werden Virtualisierung, wenn eine der folgenden Bedingungen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="b2f2e-117">Your application will be subject to virtualization if either of the following conditions is true:</span></span>  
  
1. <span data-ttu-id="b2f2e-118">Sie verwenden die `-nowin32manifest` Option, und Sie bieten kein Manifests in einem späteren Buildschritt oder als Teil einer Windows-Ressourcendatei (. res) mithilfe der `-win32resource` Option.</span><span class="sxs-lookup"><span data-stu-id="b2f2e-118">You use the `-nowin32manifest` option and you do not provide a manifest in a later build step or as part of a Windows Resource (.res) file by using the `-win32resource` option.</span></span>  
  
2. <span data-ttu-id="b2f2e-119">Sie stellen ein benutzerdefiniertes Manifest bereit, das keine angeforderte Ausführungsebene angibt.</span><span class="sxs-lookup"><span data-stu-id="b2f2e-119">You provide a custom manifest that does not specify a requested execution level.</span></span>  
  
 <span data-ttu-id="b2f2e-120">Visual Studio erstellt eine MANIFEST-Standarddatei und speichert sie zusammen mit der ausführbaren Datei in den Debug- oder Releaseverzeichnissen.</span><span class="sxs-lookup"><span data-stu-id="b2f2e-120">Visual Studio creates a default .manifest file and stores it in the debug and release directories alongside the executable file.</span></span> <span data-ttu-id="b2f2e-121">Sie können auch anzeigen oder bearbeiten Sie die Standarddatei "App.manifest" durch Klicken auf **UAC-Anzeigeeinstellungen** auf die **Anwendung** Registerkarte im Projekt-Designer.</span><span class="sxs-lookup"><span data-stu-id="b2f2e-121">You can view or edit the default app.manifest file by clicking **View UAC Settings** on the **Application** tab in the Project Designer.</span></span> <span data-ttu-id="b2f2e-122">Weitere Informationen finden Sie unter [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="b2f2e-122">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="b2f2e-123">Sie können das Anwendungsmanifest als einen benutzerdefinierten Postbuildschritt oder als Teil der Win32-Ressourcendatei bereitstellen, mit der `-nowin32manifest` Option.</span><span class="sxs-lookup"><span data-stu-id="b2f2e-123">You can provide the application manifest as a custom post-build step or as part of a Win32 resource file by using the `-nowin32manifest` option.</span></span> <span data-ttu-id="b2f2e-124">Verwenden Sie dieselbe Option, wenn Ihre Anwendung der Datei- oder Registrierungsvirtualisierung unter Windows Vista unterliegen soll.</span><span class="sxs-lookup"><span data-stu-id="b2f2e-124">Use that same option if you want your application to be subject to file or registry virtualization on Windows Vista.</span></span> <span data-ttu-id="b2f2e-125">Dadurch wird verhindert, dass den Compiler erstellt und einbettet ein Standardmanifest in der PE-Datei.</span><span class="sxs-lookup"><span data-stu-id="b2f2e-125">This will prevent the compiler from creating and embedding a default manifest in the PE file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2f2e-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b2f2e-126">Example</span></span>  
 <span data-ttu-id="b2f2e-127">Das folgende Beispiel zeigt dem Standard-Manifest, dass Visual Basic-Compiler in eine PE einfügt.</span><span class="sxs-lookup"><span data-stu-id="b2f2e-127">The following example shows the default manifest that the Visual Basic compiler inserts into a PE.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b2f2e-128">Der Compiler Fügt einen Standardanwendungsnamen MyApplication.app in das XML-Manifest.</span><span class="sxs-lookup"><span data-stu-id="b2f2e-128">The compiler inserts a standard application name MyApplication.app into the manifest XML.</span></span> <span data-ttu-id="b2f2e-129">Mit dieser Problemumgehung können Anwendungen unter Windows Server 2003 Service Pack 3 ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b2f2e-129">This is a workaround to enable applications to run on Windows Server 2003 Service Pack 3.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b2f2e-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b2f2e-130">See also</span></span>

- [<span data-ttu-id="b2f2e-131">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="b2f2e-131">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="b2f2e-132">-nowin32manifest (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b2f2e-132">-nowin32manifest (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)
