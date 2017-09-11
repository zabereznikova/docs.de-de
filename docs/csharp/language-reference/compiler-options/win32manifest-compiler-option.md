---
title: -win32manifest (C#-Compileroptionen)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /win32manifest
dev_langs:
- CSharp
helpviewer_keywords:
- /win32manifest compiler option [C#]
- win32manifest compiler option [C#]
- -win32manifest compiler option [C#]
ms.assetid: 9460ea1b-6c9f-44b8-8f73-301b30a01de1
caps.latest.revision: 13
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
ms.openlocfilehash: 938317fdf0c56469b85b1231a47f83e9c2a7d0f2
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="win32manifest-c-compiler-options"></a><span data-ttu-id="e6006-102">/win32manifest (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="e6006-102">/win32manifest (C# Compiler Options)</span></span>
<span data-ttu-id="e6006-103">Verwenden Sie die Option **/win32manifest**, um eine benutzerdefinierte Win32-Anwendungsmanifestdatei anzugeben, die in die übertragbare ausführbare Datei (portable executable, PE) eines Projekts eingebettet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e6006-103">Use the **/win32manifest** option to specify a user-defined Win32 application manifest file to be embedded into a project's portable executable (PE) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6006-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e6006-104">Syntax</span></span>  
  
```console  
/win32manifest: filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="e6006-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="e6006-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="e6006-106">Der Name und Speicherort der benutzerdefinierten Manifestdatei</span><span class="sxs-lookup"><span data-stu-id="e6006-106">The name and location of the custom manifest file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6006-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e6006-107">Remarks</span></span>  
 <span data-ttu-id="e6006-108">Standardmäßig bettet der [!INCLUDE[csharp_current_short](~/includes/csharp-current-short-md.md)]-Compiler ein Anwendungsmanifest ein, das eine angeforderte Ausführungsebene als „asInvoker“ angibt.</span><span class="sxs-lookup"><span data-stu-id="e6006-108">By default, the [!INCLUDE[csharp_current_short](~/includes/csharp-current-short-md.md)] compiler embeds an application manifest that specifies a requested execution level of "asInvoker."</span></span> <span data-ttu-id="e6006-109">Er erstellt das Manifest in demselben Ordner, in dem die ausführbare Datei erstellt wird; in der Regel ist dies der Ordner „bin\Debug“ oder „bin\Release“, wenn Sie Visual Studio verwenden.</span><span class="sxs-lookup"><span data-stu-id="e6006-109">It creates the manifest in the same folder in which the executable is built, typically the bin\Debug or bin\Release folder when you use Visual Studio.</span></span> <span data-ttu-id="e6006-110">Wenn Sie ein benutzerdefiniertes Manifest bereitstellen möchten, z.B. um eine angeforderte Ausführungsebene von „highestAvailable“ oder „requireAdministrator“ anzugeben, verwenden Sie diese Option zum Angeben des Dateinamens.</span><span class="sxs-lookup"><span data-stu-id="e6006-110">If you want to supply a custom manifest, for example to specify a requested execution level of "highestAvailable" or "requireAdministrator," use this option to specify the name of the file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e6006-111">Diese Option und die Option [/win32res (C#-Compileroptionen)](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md) schließen sich gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="e6006-111">This option and the [/win32res (C# Compiler Options)](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md) option are mutually exclusive.</span></span> <span data-ttu-id="e6006-112">Wenn Sie versuchen, beide Optionen in derselben Befehlszeile zu verwenden, erhalten Sie einen Buildfehler.</span><span class="sxs-lookup"><span data-stu-id="e6006-112">If you try to use both options in the same command line you will get a build error.</span></span>  
  
 <span data-ttu-id="e6006-113">Eine Anwendung ohne Anwendungsmanifest, das eine angeforderte Anwendungsebene angibt, unterliegt der Datei- und Registrierungsvirtualisierung unter der Benutzerkontensteuerung in Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="e6006-113">An application that has no application manifest that specifies a requested execution level will be subject to file/registry virtualization under the User Account Control feature in Windows Vista.</span></span> <span data-ttu-id="e6006-114">Weitere Informationen zur Virtualisierung finden Sie unter [Windows Vista für Entwickler: Windows Vista Anwendungsentwicklungsanforderungen für die Benutzerkontensteuerung](http://go.microsoft.com/fwlink/?LinkId=95452).</span><span class="sxs-lookup"><span data-stu-id="e6006-114">For more information about virtualization, see [The Windows Vista Developer Story: Windows Vista Application Development Requirements for User Account Control (UAC)](http://go.microsoft.com/fwlink/?LinkId=95452).</span></span>  
  
 <span data-ttu-id="e6006-115">Die Anwendung unterliegt der Virtualisierung, wenn eine dieser Bedingungen erfüllt ist:</span><span class="sxs-lookup"><span data-stu-id="e6006-115">Your application will be subject to virtualization if either of these conditions is true:</span></span>  
  
-   <span data-ttu-id="e6006-116">Sie verwenden die Option **/nowin32manifest**, und Sie stellen in einem späteren Buildschritt oder als Teil einer Windows-Ressource (.res) kein Manifest bereit, indem Sie die Option **/win32res** verwenden.</span><span class="sxs-lookup"><span data-stu-id="e6006-116">You use the **/nowin32manifest** option and you do not provide a manifest in a later build step or as part of a Windows Resource (.res) file by using the **/win32res** option.</span></span>  
  
-   <span data-ttu-id="e6006-117">Sie stellen ein benutzerdefiniertes Manifest bereit, das keine angeforderte Ausführungsebene angibt.</span><span class="sxs-lookup"><span data-stu-id="e6006-117">You provide a custom manifest that does not specify a requested execution level.</span></span>  
  
 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]<span data-ttu-id="e6006-118"> erstellt eine Standard MANIFEST-Datei und speichert sie zusammen mit der ausführbaren Datei in den Debug- oder Releaseverzeichnissen.</span><span class="sxs-lookup"><span data-stu-id="e6006-118"> creates a default .manifest file and stores it in the debug and release directories alongside the executable file.</span></span> <span data-ttu-id="e6006-119">Sie können ein benutzerdefiniertes Manifest hinzufügen, indem Sie es in einem Text-Editor erstellen und die Datei anschließend zum Projekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e6006-119">You can add a custom manifest by creating one in any text editor and then adding the file to the project.</span></span> <span data-ttu-id="e6006-120">Alternativ können Sie mit der rechten Maustaste auf das **Projekt**-Symbol im **Projektmappen-Explorer** klicken und anschließend auf **Neues Element hinzufügen** und dann auf **Anwendungsmanifestdatei** klicken.</span><span class="sxs-lookup"><span data-stu-id="e6006-120">Alternatively, you can right-click the **Project** icon in **Solution Explorer**, click **Add New Item**, and then click **Application Manifest File**.</span></span> <span data-ttu-id="e6006-121">Nachdem Sie Ihre neue oder vorhandene Manifestdatei hinzugefügt haben, wird sie in der Dropdownliste **Manifest** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e6006-121">After you have added your new or existing manifest file, it will appear in the **Manifest** drop down list.</span></span> <span data-ttu-id="e6006-122">Weitere Informationen finden Sie unter [Seite „Anwendung“, Projekt-Designer (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="e6006-122">For more information, see [Application Page, Project Designer (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).</span></span>  
  
 <span data-ttu-id="e6006-123">Sie können das Anwendungsmanifest über einen benutzerdefinierten Postbuildschritt oder als Teil einer Win32-Ressourcendatei bereitstellen, indem Sie die Option [/nowin32manifest (C#-Compileroptionen)](../../../csharp/language-reference/compiler-options/nowin32manifest-compiler-option.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="e6006-123">You can provide the application manifest as a custom post-build step or as part of a Win32 resource file by using the [/nowin32manifest (C# Compiler Options)](../../../csharp/language-reference/compiler-options/nowin32manifest-compiler-option.md) option.</span></span> <span data-ttu-id="e6006-124">Verwenden Sie dieselbe Option, wenn Ihre Anwendung der Datei- oder Registrierungsvirtualisierung unter Windows Vista unterliegen soll.</span><span class="sxs-lookup"><span data-stu-id="e6006-124">Use that same option if you want your application to be subject to file or registry virtualization on Windows Vista.</span></span> <span data-ttu-id="e6006-125">Dies verhindert, dass der Compiler ein Standardmanifest in der portierbaren ausführbaren Datei (portable executable, PE) erstellt und einbettet.</span><span class="sxs-lookup"><span data-stu-id="e6006-125">This will prevent the compiler from creating and embedding a default manifest in the portable executable (PE) file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6006-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e6006-126">Example</span></span>  
 <span data-ttu-id="e6006-127">Im folgenden Beispiel wird das Standardmanifest gezeigt, das der Visual C# Compiler in eine PE einfügt.</span><span class="sxs-lookup"><span data-stu-id="e6006-127">The following example shows the default manifest that the Visual C# compiler inserts into a PE.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e6006-128">Der Compiler fügt einen Standardanwendungsnamen, „MyApplication.app“, in die XML-Datei ein.</span><span class="sxs-lookup"><span data-stu-id="e6006-128">The compiler inserts a standard application name " MyApplication.app " into the xml.</span></span> <span data-ttu-id="e6006-129">Mit dieser Problemumgehung können Anwendungen unter Windows Server 2003 Service Pack 3 ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e6006-129">This is a workaround to enable applications to run on Windows Server 2003 Service Pack 3.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e6006-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6006-130">See Also</span></span>  
 <span data-ttu-id="e6006-131">[C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="e6006-131">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 <span data-ttu-id="e6006-132">[/nowin32manifest (C#-Compileroptionen)](../../../csharp/language-reference/compiler-options/nowin32manifest-compiler-option.md) </span><span class="sxs-lookup"><span data-stu-id="e6006-132">[/nowin32manifest (C# Compiler Options)](../../../csharp/language-reference/compiler-options/nowin32manifest-compiler-option.md) </span></span>  
 [<span data-ttu-id="e6006-133">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="e6006-133">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

