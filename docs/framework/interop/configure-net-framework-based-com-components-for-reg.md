---
title: 'Gewusst wie: Konfigurieren von .NET Framework-basierten COM-Komponenten für die registrierungsfreie Aktivierung'
ms.date: 03/30/2017
helpviewer_keywords:
- components [.NET Framework], manifest
- application manifests [.NET Framework]
- manifests [.NET Framework]
- registration-free COM interop, configuring .NET-based components
- activation, registration-free
ms.assetid: 32f8b7c6-3f73-455d-8e13-9846895bd43b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d9df1aa781bd54468d2273a335b3fda7d701854d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43519407"
---
# <a name="how-to-configure-net-framework-based-com-components-for-registration-free-activation"></a><span data-ttu-id="3cd38-102">Gewusst wie: Konfigurieren von .NET Framework-basierten COM-Komponenten für die registrierungsfreie Aktivierung</span><span class="sxs-lookup"><span data-stu-id="3cd38-102">How to: Configure .NET Framework-Based COM Components for Registration-Free Activation</span></span>
<span data-ttu-id="3cd38-103">Die Aktivierung ohne Registrierung ist bei .NET Framework-Komponenten nur geringfügig schwieriger als bei COM-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="3cd38-103">Registration-free activation for .NET Framework-based components is only slightly more complicated than it is for COM components.</span></span> <span data-ttu-id="3cd38-104">Für das Setup sind zwei Manifeste erforderlich:</span><span class="sxs-lookup"><span data-stu-id="3cd38-104">The setup requires two manifests:</span></span>  
  
-   <span data-ttu-id="3cd38-105">COM-Anwendungen müssen über ein Win32-Anwendungsmanifest verfügen, um die verwaltete Komponente zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="3cd38-105">COM applications must have a Win32-style application manifest to identify the managed component.</span></span>  
  
-   <span data-ttu-id="3cd38-106">.NET Framework-Komponenten müssen über ein Komponentenmanifest mit den zur Laufzeit erforderlichen Aktivierungsinformationen verfügen.</span><span class="sxs-lookup"><span data-stu-id="3cd38-106">.NET Framework-based components must have a component manifest for activation information needed at run time.</span></span>  
  
 <span data-ttu-id="3cd38-107">In diesem Thema werden das Zuordnen eines Anwendungsmanifests zu einer Anwendung, das Zuordnen eines Komponentenmanifests zu einer Komponente und das Einbetten eines Komponentenmanifests in eine Assembly beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3cd38-107">This topic describes how to associate an application manifest with an application; associate a component manifest with a component; and embed a component manifest in an assembly.</span></span>  
  
### <a name="to-create-an-application-manifest"></a><span data-ttu-id="3cd38-108">So erstellen Sie ein Anwendungsmanifest</span><span class="sxs-lookup"><span data-stu-id="3cd38-108">To create an application manifest</span></span>  
  
1.  <span data-ttu-id="3cd38-109">Erstellen oder bearbeiten Sie mit einem XML-Editor das Anwendungsmanifest der COM-Anwendung, die mit einer oder mehreren verwalteten Komponenten interoperiert.</span><span class="sxs-lookup"><span data-stu-id="3cd38-109">Using an XML editor, create (or modify) the application manifest owned by the COM application that is interoperating with one or more managed components.</span></span>  
  
2.  <span data-ttu-id="3cd38-110">Fügen Sie am Anfang der Datei den folgenden Standardheader ein:</span><span class="sxs-lookup"><span data-stu-id="3cd38-110">Insert the following standard header at the beginning of the file:</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
    ```  
  
     <span data-ttu-id="3cd38-111">Weitere Informationen über Elemente von Manifesten und deren Attribute finden Sie unter [Anwendungsmanifeste](/windows/desktop/SbsCs/application-manifests).</span><span class="sxs-lookup"><span data-stu-id="3cd38-111">For information about manifest elements and their attributes, see [Application Manifests](/windows/desktop/SbsCs/application-manifests).</span></span>  
  
3.  <span data-ttu-id="3cd38-112">Bestimmen Sie den Besitzer des Manifests.</span><span class="sxs-lookup"><span data-stu-id="3cd38-112">Identify the owner of the manifest.</span></span> <span data-ttu-id="3cd38-113">Im folgenden Beispiel ist `myComApp`, Version 1, Besitzer der Manifestdatei.</span><span class="sxs-lookup"><span data-stu-id="3cd38-113">In the following example, `myComApp` version 1 owns the manifest file.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
      <assemblyIdentity type="win32"   
                        name="myOrganization.myDivision.myComApp"   
                        version="1.0.0.0"   
                        processorArchitecture="msil"   
      />  
    ```  
  
4.  <span data-ttu-id="3cd38-114">Bestimmen Sie die abhängigen Assemblys.</span><span class="sxs-lookup"><span data-stu-id="3cd38-114">Identify dependent assemblies.</span></span> <span data-ttu-id="3cd38-115">Im folgenden Beispiel ist `myComApp` von `myManagedComp` abhängig.</span><span class="sxs-lookup"><span data-stu-id="3cd38-115">In the following example, `myComApp` depends on `myManagedComp`.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
      <assemblyIdentity type="win32"   
                        name="myOrganization.myDivision.myComApp"   
                        version="1.0.0.0"   
                        processorArchitecture="x86"   
                        publicKeyToken="8275b28176rcbbef"  
      />  
      <dependency>  
        <dependentAssembly>  
          <assemblyIdentity type="win32"   
                        name="myOrganization.myDivision.myManagedComp"   
                        version="6.0.0.0"   
                        processorArchitecture="X86"   
                        publicKeyToken="8275b28176rcbbef"  
          />  
        </dependentAssembly>  
      </dependency>  
    </assembly>  
    ```  
  
5.  <span data-ttu-id="3cd38-116">Speichern und benennen Sie die Manifestdatei.</span><span class="sxs-lookup"><span data-stu-id="3cd38-116">Save and name the manifest file.</span></span> <span data-ttu-id="3cd38-117">Der Name eines Anwendungsmanifests besteht aus dem Namen der ausführbaren Assembly gefolgt von der Erweiterung MANIFEST.</span><span class="sxs-lookup"><span data-stu-id="3cd38-117">The name of an application manifest is the name of the assembly executable followed by the .manifest extension.</span></span> <span data-ttu-id="3cd38-118">Der Dateiname des Anwendungsmanifests für myComApp.exe lautet z. B. myComApp.exe.manifest.</span><span class="sxs-lookup"><span data-stu-id="3cd38-118">For example, the application manifest file name for myComApp.exe is myComApp.exe.manifest.</span></span>  
  
 <span data-ttu-id="3cd38-119">Sie können ein Anwendungsmanifest im gleichen Verzeichnis wie die COM-Anwendung installieren.</span><span class="sxs-lookup"><span data-stu-id="3cd38-119">You can install an application manifest in the same directory as the COM application.</span></span> <span data-ttu-id="3cd38-120">Sie können es aber auch der EXE-Datei der Anwendung als eine Ressource hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3cd38-120">Alternatively, you can add it as a resource to the application's .exe file.</span></span> <span data-ttu-id="3cd38-121">Weitere Informationen finden Sie unter [About Side-by-Side Assemblies (Parallele Assemblys)](/windows/desktop/SbsCs/about-side-by-side-assemblies-).</span><span class="sxs-lookup"><span data-stu-id="3cd38-121">For additional information, For more information, see [About Side-by-Side Assemblies](/windows/desktop/SbsCs/about-side-by-side-assemblies-).</span></span>  
  
#### <a name="to-create-a-component-manifest"></a><span data-ttu-id="3cd38-122">So erstellen Sie ein Komponentenmanifest</span><span class="sxs-lookup"><span data-stu-id="3cd38-122">To create a component manifest</span></span>  
  
1.  <span data-ttu-id="3cd38-123">Erstellen Sie mit einem XML-Editor ein Komponentenmanifest, um die verwaltete Assembly zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="3cd38-123">Using an XML editor, create a component manifest to describe the managed assembly.</span></span>  
  
2.  <span data-ttu-id="3cd38-124">Fügen Sie am Anfang der Datei den folgenden Standardheader ein:</span><span class="sxs-lookup"><span data-stu-id="3cd38-124">Insert the following standard header at the beginning of the file:</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
    ```  
  
3.  <span data-ttu-id="3cd38-125">Bestimmen Sie den Besitzer der Datei.</span><span class="sxs-lookup"><span data-stu-id="3cd38-125">Identify the owner of the file.</span></span> <span data-ttu-id="3cd38-126">Das `<assemblyIdentity>`-Element des `<dependentAssembly>`-Elements in der Anwendungsmanifestdatei muss mit dem entsprechenden Element im Komponentenmanifest übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="3cd38-126">The `<assemblyIdentity>` element of the `<dependentAssembly>` element in application manifest file must match the one in the component manifest.</span></span> <span data-ttu-id="3cd38-127">Im folgenden Beispiel ist `myManagedComp`, Version 1.2.3.4, Besitzer der Manifestdatei.</span><span class="sxs-lookup"><span data-stu-id="3cd38-127">In the following example, `myManagedComp` version 1.2.3.4 owns the manifest file.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
           <assemblyIdentity  
                        name="myOrganization.myDivision.myManagedComp"  
                        version="1.2.3.4"  
                        publicKeyToken="8275b28176rcbbef"  
                        processorArchitecture="msil"  
           />  
    ```  
  
4.  <span data-ttu-id="3cd38-128">Bestimmen Sie alle Klassen in der Assembly.</span><span class="sxs-lookup"><span data-stu-id="3cd38-128">Identify each class in the assembly.</span></span> <span data-ttu-id="3cd38-129">Verwenden Sie das `<clrClass>`-Element, um die einzelnen Klassen in der verwalteten Assembly eindeutig zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="3cd38-129">Use the `<clrClass>` element to uniquely identify each class in the managed assembly.</span></span> <span data-ttu-id="3cd38-130">Das Element, das ein Unterelement des `<assembly>`-Elements ist, verfügt über die in der folgenden Tabelle beschriebenen Attribute.</span><span class="sxs-lookup"><span data-stu-id="3cd38-130">The element, which is a subelement of the `<assembly>` element, has the attributes described in the following table.</span></span>  
  
    |<span data-ttu-id="3cd38-131">Attribut</span><span class="sxs-lookup"><span data-stu-id="3cd38-131">Attribute</span></span>|<span data-ttu-id="3cd38-132">Beschreibung </span><span class="sxs-lookup"><span data-stu-id="3cd38-132">Description</span></span>|<span data-ttu-id="3cd38-133">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="3cd38-133">Required</span></span>|  
    |---------------|-----------------|--------------|  
    |`clsid`|<span data-ttu-id="3cd38-134">Der Bezeichner, der die zu aktivierende Klasse kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="3cd38-134">The identifier that specifies the class to be activated.</span></span>|<span data-ttu-id="3cd38-135">Ja</span><span class="sxs-lookup"><span data-stu-id="3cd38-135">Yes</span></span>|  
    |`description`|<span data-ttu-id="3cd38-136">Eine Zeichenfolge, die Benutzer über die Komponente informiert.</span><span class="sxs-lookup"><span data-stu-id="3cd38-136">A string that informs the user about the component.</span></span> <span data-ttu-id="3cd38-137">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="3cd38-137">An empty string is the default.</span></span>|<span data-ttu-id="3cd38-138">Nein</span><span class="sxs-lookup"><span data-stu-id="3cd38-138">No</span></span>|  
    |`name`|<span data-ttu-id="3cd38-139">Eine Zeichenfolge, die die verwaltete Klasse darstellt.</span><span class="sxs-lookup"><span data-stu-id="3cd38-139">A string that represents the managed class.</span></span>|<span data-ttu-id="3cd38-140">Ja</span><span class="sxs-lookup"><span data-stu-id="3cd38-140">Yes</span></span>|  
    |`progid`|<span data-ttu-id="3cd38-141">Der Bezeichner für die spät gebundene Aktivierung.</span><span class="sxs-lookup"><span data-stu-id="3cd38-141">The identifier to be used for late-bound activation.</span></span>|<span data-ttu-id="3cd38-142">Nein</span><span class="sxs-lookup"><span data-stu-id="3cd38-142">No</span></span>|  
    |`threadingModel`|<span data-ttu-id="3cd38-143">Das COM-Threadingmodell.</span><span class="sxs-lookup"><span data-stu-id="3cd38-143">The COM threading model.</span></span> <span data-ttu-id="3cd38-144">Der Standardwert ist "Both".</span><span class="sxs-lookup"><span data-stu-id="3cd38-144">"Both" is the default value.</span></span>|<span data-ttu-id="3cd38-145">Nein</span><span class="sxs-lookup"><span data-stu-id="3cd38-145">No</span></span>|  
    |`runtimeVersion`|<span data-ttu-id="3cd38-146">Gibt die zu verwendende Common Language Runtime-Version (CLR) an.</span><span class="sxs-lookup"><span data-stu-id="3cd38-146">Specifies the common language runtime (CLR) version to use.</span></span> <span data-ttu-id="3cd38-147">Wenn Sie dieses Attribut nicht angeben und die CLR nicht bereits geladen ist, wird die Komponente mit der neuesten installierten CLR vor CLR-Version 4 geladen.</span><span class="sxs-lookup"><span data-stu-id="3cd38-147">If you do not specify this attribute, and the CLR is not already loaded, the component is loaded with the latest installed CLR prior to CLR version 4.</span></span> <span data-ttu-id="3cd38-148">Wenn Sie v1.0.3705, v1.1.4322 oder v2.0.50727 angeben, wird für die Version automatisch ein Rollforward auf die neueste installierte CLR-Version vor CLR-Version 4 ausgeführt (normalerweise v2.0.50727).</span><span class="sxs-lookup"><span data-stu-id="3cd38-148">If you specify v1.0.3705, v1.1.4322, or v2.0.50727, the version automatically rolls forward to the latest installed CLR version prior to CLR version 4 (usually v2.0.50727).</span></span> <span data-ttu-id="3cd38-149">Falls eine andere Version der CLR bereits geladen ist und die angegebene Version prozessintern parallel geladen werden kann, wird die angegebene Version geladen. Andernfalls wird die geladene CLR verwendet.</span><span class="sxs-lookup"><span data-stu-id="3cd38-149">If another version of the CLR is already loaded and the specified version can be loaded side-by-side in-process, the specified version is loaded; otherwise, the loaded CLR is used.</span></span> <span data-ttu-id="3cd38-150">Dies kann beim Laden einen Fehler verursachen.</span><span class="sxs-lookup"><span data-stu-id="3cd38-150">This might cause a load failure.</span></span>|<span data-ttu-id="3cd38-151">Nein</span><span class="sxs-lookup"><span data-stu-id="3cd38-151">No</span></span>|  
    |`tlbid`|<span data-ttu-id="3cd38-152">Der Bezeichner der Typbibliothek mit den Typeninformationen über die Klasse.</span><span class="sxs-lookup"><span data-stu-id="3cd38-152">The identifier of the type library that contains type information about the class.</span></span>|<span data-ttu-id="3cd38-153">Nein</span><span class="sxs-lookup"><span data-stu-id="3cd38-153">No</span></span>|  
  
     <span data-ttu-id="3cd38-154">Bei allen Attributtags muss die Groß- und Kleinschreibung beachtet werden.</span><span class="sxs-lookup"><span data-stu-id="3cd38-154">All attribute tags are case-sensitive.</span></span> <span data-ttu-id="3cd38-155">Sie können CLSIDs, ProgIDs, Threadingmodelle und die Version der Common Language Runtime ermitteln, indem Sie die exportierte Typbibliothek der Assembly mit dem OLE/COM-Objektkatalog (Oleview.exe) anzeigen.</span><span class="sxs-lookup"><span data-stu-id="3cd38-155">You can obtain CLSIDs, ProgIDs, threading models, and the runtime version by viewing the exported type library for the assembly with the OLE/COM ObjectViewer (Oleview.exe).</span></span>  
  
     <span data-ttu-id="3cd38-156">Das folgende Komponentenmanifest identifiziert die beiden Klassen `testClass1` und `testClass2`.</span><span class="sxs-lookup"><span data-stu-id="3cd38-156">The following component manifest identifies two classes, `testClass1` and `testClass2`.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
           <assemblyIdentity  
                        name="myOrganization.myDivision.myManagedComp"  
                        version="1.2.3.4"   
                        publicKeyToken="8275b28176rcbbef"  
           />  
           <clrClass  
                        clsid="{65722BE6-3449-4628-ABD3-74B6864F9739}"  
                        progid="myManagedComp.testClass1"  
                        threadingModel="Both"  
                        name="myManagedComp.testClass1"  
                        runtimeVersion="v1.0.3705">  
           </clrClass>  
           <clrClass  
                        clsid="{367221D6-3559-3328-ABD3-45B6825F9732}"  
                        progid="myManagedComp.testClass2"  
                        threadingModel="Both"  
                        name="myManagedComp.testClass2"  
                        runtimeVersion="v1.0.3705">  
           </clrClass>  
           <file name="MyManagedComp.dll">  
           </file>  
    </assembly>  
    ```  
  
5.  <span data-ttu-id="3cd38-157">Speichern und benennen Sie die Manifestdatei.</span><span class="sxs-lookup"><span data-stu-id="3cd38-157">Save and name the manifest file.</span></span> <span data-ttu-id="3cd38-158">Der Name eines Komponentenmanifests besteht aus dem Namen der Assemblybibliothek gefolgt von der Erweiterung MANIFEST.</span><span class="sxs-lookup"><span data-stu-id="3cd38-158">The name of a component manifest is the name of the assembly library followed by the .manifest extension.</span></span> <span data-ttu-id="3cd38-159">Das Manifest zu myManagedComp.dll lautet z. B. myManagedComp.manifest.</span><span class="sxs-lookup"><span data-stu-id="3cd38-159">For example, the myManagedComp.dll is myManagedComp.manifest.</span></span>  
  
 <span data-ttu-id="3cd38-160">Sie müssen das Komponentenmanifest als eine Ressource in die Assembly einbetten.</span><span class="sxs-lookup"><span data-stu-id="3cd38-160">You must embed the component manifest as a resource in the assembly.</span></span>  
  
#### <a name="to-embed-a-component-manifest-in-a-managed-assembly"></a><span data-ttu-id="3cd38-161">So betten Sie ein Komponentenmanifest in eine verwaltete Assembly ein</span><span class="sxs-lookup"><span data-stu-id="3cd38-161">To embed a component manifest in a managed assembly</span></span>  
  
1.  <span data-ttu-id="3cd38-162">Erstellen Sie ein Ressourcenskript, das die folgende Anweisung enthält:</span><span class="sxs-lookup"><span data-stu-id="3cd38-162">Create a resource script that contains the following statement:</span></span>  
  
     `RT_MANIFEST 1 myManagedComp.manifest`  
  
     <span data-ttu-id="3cd38-163">In dieser Anweisung ist `myManagedComp.manifest` der Name des einzubettenden Komponentenmanifests.</span><span class="sxs-lookup"><span data-stu-id="3cd38-163">In this statement, `myManagedComp.manifest` is the name of the component manifest being embedded.</span></span> <span data-ttu-id="3cd38-164">Der Name der Skriptdatei für dieses Beispiel lautet `myresource.rc`.</span><span class="sxs-lookup"><span data-stu-id="3cd38-164">For this example, the script file name is `myresource.rc`.</span></span>  
  
2.  <span data-ttu-id="3cd38-165">Kompilieren Sie das Skript mit dem Ressourcencompiler von Microsoft Windows (Rc.exe).</span><span class="sxs-lookup"><span data-stu-id="3cd38-165">Compile the script using the Microsoft Windows Resource Compiler (Rc.exe).</span></span> <span data-ttu-id="3cd38-166">Geben Sie an der Eingabeaufforderung folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="3cd38-166">At the command prompt, type the following command:</span></span>  
  
     `rc myresource.rc`  
  
     <span data-ttu-id="3cd38-167">Rc.exe erstellt die Ressourcendatei `myresource.res`.</span><span class="sxs-lookup"><span data-stu-id="3cd38-167">Rc.exe produces the `myresource.res` resource file.</span></span>  
  
3.  <span data-ttu-id="3cd38-168">Kompilieren Sie die Quelldatei der Assembly erneut, und geben Sie die Ressourcendatei mit der Option **/win32res** an:</span><span class="sxs-lookup"><span data-stu-id="3cd38-168">Compile the assembly's source file again and specify the resource file by using the **/win32res** option:</span></span>  
  
    ```  
    /win32res:myresource.res  
    ```  
  
     <span data-ttu-id="3cd38-169">Auch hier ist `myresource.res` der Name der Ressourcendatei mit der eingebetteten Ressource.</span><span class="sxs-lookup"><span data-stu-id="3cd38-169">Again, `myresource.res` is the name of the resource file containing embedded resource.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cd38-170">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3cd38-170">See Also</span></span>  
 [<span data-ttu-id="3cd38-171">COM-Interop ohne Registrierung</span><span class="sxs-lookup"><span data-stu-id="3cd38-171">Registration-Free COM Interop</span></span>](registration-free-com-interop.md)  
 <span data-ttu-id="3cd38-172">[Anforderungen an COM-Interop ohne Registrierung](https://msdn.microsoft.com/library/0c43bc57-eecf-4e6c-8114-490141cce4da(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="3cd38-172">[Requirements for Registration-Free COM Interop](https://msdn.microsoft.com/library/0c43bc57-eecf-4e6c-8114-490141cce4da(v=vs.100)))</span></span>  
 <span data-ttu-id="3cd38-173">[Konfigurieren von COM-Komponenten für eine Aktivierung ohne Registrierung](https://msdn.microsoft.com/library/bfe9b02f-d964-4784-960e-a1f94692fbfe(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="3cd38-173">[Configuring COM Components for Registration-Free Activation](https://msdn.microsoft.com/library/bfe9b02f-d964-4784-960e-a1f94692fbfe(v=vs.100)))</span></span>  
 [<span data-ttu-id="3cd38-174">Registration-Free Activation of .NET-Based Components: A Walkthrough (Exemplarische Vorgehensweise: Aktivierung der .NET-basierten Komponenten ohne Registrierung)</span><span class="sxs-lookup"><span data-stu-id="3cd38-174">Registration-Free Activation of .NET-Based Components: A Walkthrough</span></span>](https://msdn.microsoft.com/library/ms973915.aspx)
