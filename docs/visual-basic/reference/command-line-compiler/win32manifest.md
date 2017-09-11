---
title: /win32manifest (Visual Basic) | Microsoft-Dokumentation
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
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
caps.latest.revision: 9
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
ms.openlocfilehash: 4a9693bd7eb03dee5a2a9f2d43360b963e9fd876
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="win32manifest-visual-basic"></a><span data-ttu-id="8ca4c-102">/win32manifest (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8ca4c-102">/win32manifest (Visual Basic)</span></span>
<span data-ttu-id="8ca4c-103">Identifiziert eine benutzerdefinierte Win32-Anwendungsmanifestdatei, die in die übertragbare ausführbare Datei (PE) eines Projekts eingebettet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8ca4c-103">Identifies a user-defined Win32 application manifest file to be embedded into a project's portable executable (PE) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ca4c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8ca4c-104">Syntax</span></span>  
  
```  
/win32manifest: fileName  
```  
  
## <a name="arguments"></a><span data-ttu-id="8ca4c-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="8ca4c-105">Arguments</span></span>  
  
|<span data-ttu-id="8ca4c-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="8ca4c-106">Term</span></span>|<span data-ttu-id="8ca4c-107">Definition</span><span class="sxs-lookup"><span data-stu-id="8ca4c-107">Definition</span></span>|  
|---|---|  
|`fileName`|<span data-ttu-id="8ca4c-108">Der Pfad der benutzerdefinierten Manifestdatei.</span><span class="sxs-lookup"><span data-stu-id="8ca4c-108">The path of the custom manifest file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ca4c-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8ca4c-109">Remarks</span></span>  
 <span data-ttu-id="8ca4c-110">Standardmäßig bettet der Visual Basic-Compiler ein Anwendungsmanifest eine angeforderte Ausführungsebene "asInvoker" angibt.</span><span class="sxs-lookup"><span data-stu-id="8ca4c-110">By default, the Visual Basic compiler embeds an application manifest that specifies a requested execution level of asInvoker.</span></span> <span data-ttu-id="8ca4c-111">Das Manifest erstellt in demselben Ordner, in dem die ausführbare Datei erstellt wird, in der Regel Ordner Bin\Debug oder Bin\Release bei Verwendung von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8ca4c-111">It creates the manifest in the same folder in which the executable file is built, typically the bin\Debug or bin\Release folder when you use Visual Studio.</span></span> <span data-ttu-id="8ca4c-112">Wenn Sie möchten ein benutzerdefiniertes Manifest, z. B. zum Festlegen einer angeforderten Ausführungsebene "highestAvailable" oder "requireAdministrator", verwenden Sie diese Option den Namen der Datei angeben.</span><span class="sxs-lookup"><span data-stu-id="8ca4c-112">If you want to supply a custom manifest, for example to specify a requested execution level of highestAvailable or requireAdministrator, use this option to specify the name of the file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8ca4c-113">Diese Option und die [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) Option schließen sich gegenseitig.</span><span class="sxs-lookup"><span data-stu-id="8ca4c-113">This option and the [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) option are mutually exclusive.</span></span> <span data-ttu-id="8ca4c-114">Wenn Sie versuchen, in derselben Befehlszeile beide Optionen verwenden, erhalten Sie einen Buildfehler.</span><span class="sxs-lookup"><span data-stu-id="8ca4c-114">If you try to use both options in the same command line, you will get a build error.</span></span>  
  
 <span data-ttu-id="8ca4c-115">Eine Anwendung ohne Anwendungsmanifest gibt an, dass eine angeforderte Ausführungsebene unterliegen Datei-/Registrierungsvirtualisierung der Benutzerkontensteuerung in Windows Vista ist.</span><span class="sxs-lookup"><span data-stu-id="8ca4c-115">An application that has no application manifest that specifies a requested execution level will be subject to file/registry virtualization under the User Account Control feature in Windows Vista.</span></span> <span data-ttu-id="8ca4c-116">Weitere Informationen zur Virtualisierung finden Sie unter [ClickOnce-Bereitstellung unter Windows Vista](https://docs.microsoft.com/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span><span class="sxs-lookup"><span data-stu-id="8ca4c-116">For more information about virtualization, see [ClickOnce Deployment on Windows Vista](https://docs.microsoft.com/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span></span>  
  
 <span data-ttu-id="8ca4c-117">Die Anwendung wird Virtualisierung sein, wenn eine der folgenden Situationen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="8ca4c-117">Your application will be subject to virtualization if either of the following conditions is true:</span></span>  
  
1.  <span data-ttu-id="8ca4c-118">Verwenden Sie die `/nowin32manifest` Option, und Sie bieten kein Manifest in einem späteren Buildschritt oder als Teil einer Windows-Ressource (res)-Datei mithilfe der `/win32resource` Option.</span><span class="sxs-lookup"><span data-stu-id="8ca4c-118">You use the `/nowin32manifest` option and you do not provide a manifest in a later build step or as part of a Windows Resource (.res) file by using the `/win32resource` option.</span></span>  
  
2.  <span data-ttu-id="8ca4c-119">Sie geben ein benutzerdefiniertes Manifest, das keine angeforderte Ausführungsebene angibt.</span><span class="sxs-lookup"><span data-stu-id="8ca4c-119">You provide a custom manifest that does not specify a requested execution level.</span></span>  
  
 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]<span data-ttu-id="8ca4c-120">erstellt eine Standardmanifestdatei und speichert sie in den Verzeichnissen Debug- und zusammen mit der ausführbaren Datei.</span><span class="sxs-lookup"><span data-stu-id="8ca4c-120"> creates a default .manifest file and stores it in the debug and release directories alongside the executable file.</span></span> <span data-ttu-id="8ca4c-121">Sie können anzeigen oder bearbeiten Sie die Standarddatei app.manifest durch Klicken auf **UAC-Anzeigeeinstellungen** auf der **Anwendung** Registerkarte im Projekt-Designer.</span><span class="sxs-lookup"><span data-stu-id="8ca4c-121">You can view or edit the default app.manifest file by clicking **View UAC Settings** on the **Application** tab in the Project Designer.</span></span> <span data-ttu-id="8ca4c-122">Weitere Informationen finden Sie unter [Anwendungsseite, Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="8ca4c-122">For more information, see [Application Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="8ca4c-123">Sie können das Anwendungsmanifest einer benutzerdefinierten Postbuildschritt oder als Teil einer Win32-Ressourcendatei bereitstellen, mit der `/nowin32manifest` Option.</span><span class="sxs-lookup"><span data-stu-id="8ca4c-123">You can provide the application manifest as a custom post-build step or as part of a Win32 resource file by using the `/nowin32manifest` option.</span></span> <span data-ttu-id="8ca4c-124">Verwenden Sie dieselbe Option, wenn Sie Ihre Anwendung unter Windows Vista der Datei- oder Registrierungsvirtualisierung unterliegen soll.</span><span class="sxs-lookup"><span data-stu-id="8ca4c-124">Use that same option if you want your application to be subject to file or registry virtualization on Windows Vista.</span></span> <span data-ttu-id="8ca4c-125">Dies verhindert, dass der Compiler erstellt und eine Standard-Manifest in die PE-Datei einbetten.</span><span class="sxs-lookup"><span data-stu-id="8ca4c-125">This will prevent the compiler from creating and embedding a default manifest in the PE file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ca4c-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8ca4c-126">Example</span></span>  
 <span data-ttu-id="8ca4c-127">Im folgende Beispiel enthält dem Standardmanifest, Visual Basic-Compiler in eine PE eingefügt.</span><span class="sxs-lookup"><span data-stu-id="8ca4c-127">The following example shows the default manifest that the Visual Basic compiler inserts into a PE.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8ca4c-128">Der Compiler Fügt eine standardmäßige Anwendungsname MyApplication.app eingefügt, in das XML-Manifest.</span><span class="sxs-lookup"><span data-stu-id="8ca4c-128">The compiler inserts a standard application name MyApplication.app into the manifest XML.</span></span> <span data-ttu-id="8ca4c-129">Dies ist eine Lösung zum Aktivieren von Anwendungen auf Windows Server 2003 Service Pack 3 ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8ca4c-129">This is a workaround to enable applications to run on Windows Server 2003 Service Pack 3.</span></span>  
  
```  
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
  
## <a name="see-also"></a><span data-ttu-id="8ca4c-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ca4c-130">See Also</span></span>  
 <span data-ttu-id="8ca4c-131">[Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="8ca4c-131">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="8ca4c-132"> [/NoWin32Manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)</span><span class="sxs-lookup"><span data-stu-id="8ca4c-132"> [/nowin32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)</span></span>
