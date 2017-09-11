---
title: 'Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys in Visual Studio (C#)'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 55ed13c9-c5bb-4bc2-bcd8-0587eb568864
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7b003e76229a06883adc22f933f08663330f0c9d
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="walkthrough-embedding-types-from-managed-assemblies-in-visual-studio-c"></a><span data-ttu-id="bfb95-102">Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys in Visual Studio (C#)</span><span class="sxs-lookup"><span data-stu-id="bfb95-102">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (C#)</span></span>
<span data-ttu-id="bfb95-103">Wenn Sie Typinformationen von einer verwalteten Assembly mit starkem Namen einbetten, können Sie Typen in einer Anwendung lose koppeln, um versionsunabhängig zu werden.</span><span class="sxs-lookup"><span data-stu-id="bfb95-103">If you embed type information from a strong-named managed assembly, you can loosely couple types in an application to achieve version independence.</span></span> <span data-ttu-id="bfb95-104">Ihr Programm kann daher für Typen aus unterschiedlichen Versionen einer verwalteten Bibliothek geschrieben werden; eine erneute Kompilierung für jede Version ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="bfb95-104">That is, your program can be written to use types from multiple versions of a managed library without having to be recompiled for each version.</span></span>  
  
 <span data-ttu-id="bfb95-105">Das Einbetten von Typen wird häufig mit COM-Interop verwendet, z.B. mit einer Anwendung, die Automatisierungsobjekte von Microsoft Office verwendet.</span><span class="sxs-lookup"><span data-stu-id="bfb95-105">Type embedding is frequently used with COM interop, such as an application that uses automation objects from Microsoft Office.</span></span> <span data-ttu-id="bfb95-106">Das Einbetten von Typinformationen lässt zu, dass derselbe Build eines Programms mit unterschiedlichen Versionen von Microsoft Office auf verschiedenen Computern verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="bfb95-106">Embedding type information enables the same build of a program to work with different versions of Microsoft Office on different computers.</span></span> <span data-ttu-id="bfb95-107">Sie können das Einbetten von Typen jedoch auch mit einer vollständig verwalteten Anwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="bfb95-107">However, you can also use type embedding with a fully managed solution.</span></span>  
  
 <span data-ttu-id="bfb95-108">Typinformationen können von einer Assembly aus eingebettet werden, die die folgenden Merkmale aufweist:</span><span class="sxs-lookup"><span data-stu-id="bfb95-108">Type information can be embedded from an assembly that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="bfb95-109">Die Assembly macht mindestens eine öffentliche Schnittstelle verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bfb95-109">The assembly exposes at least one public interface.</span></span>  
  
-   <span data-ttu-id="bfb95-110">Die eingebetteten Schnittstellen werden mit einem `ComImport`-Attribut und einem `Guid`-Attribut (und einer eindeutigen GUID) kommentiert.</span><span class="sxs-lookup"><span data-stu-id="bfb95-110">The embedded interfaces are annotated with a `ComImport` attribute and a `Guid` attribute (and a unique GUID).</span></span>  
  
-   <span data-ttu-id="bfb95-111">Die Assembly wird mit dem `ImportedFromTypeLib`-Attribut oder dem `PrimaryInteropAssembly`-Attribut und einem `Guid`-Attribut auf Assemblyebene kommentiert.</span><span class="sxs-lookup"><span data-stu-id="bfb95-111">The assembly is annotated with the `ImportedFromTypeLib` attribute or the `PrimaryInteropAssembly` attribute, and an assembly-level `Guid` attribute.</span></span> <span data-ttu-id="bfb95-112">(Standardmäßig enthalten Visual C#-Projektvorlagen ein `Guid`-Attribut auf Assemblyebene.)</span><span class="sxs-lookup"><span data-stu-id="bfb95-112">(By default, Visual C# project templates include an assembly-level `Guid` attribute.)</span></span>  
  
 <span data-ttu-id="bfb95-113">Nachdem Sie die öffentlichen Schnittstellen angegeben haben, die eingebettet werden können, können Sie Laufzeitklassen erstellen, die diese Schnittstellen implementieren.</span><span class="sxs-lookup"><span data-stu-id="bfb95-113">After you have specified the public interfaces that can be embedded, you can create runtime classes that implement those interfaces.</span></span> <span data-ttu-id="bfb95-114">Ein Clientprogramm kann dann die Typinformationen für diese Schnittstellen zur Entwurfszeit einbetten, indem auf die Assembly verwiesen wird, die die öffentlichen Schnittstellen enthält und die Eigenschaft `Embed Interop Types` des Verweises auf `True` festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="bfb95-114">A client program can then embed the type information for those interfaces at design time by referencing the assembly that contains the public interfaces and setting the `Embed Interop Types` property of the reference to `True`.</span></span> <span data-ttu-id="bfb95-115">Dies entspricht dem Verwenden des Befehlszeilencompilers und Verweisen auf die Assembly mit der Compileroption `/link`.</span><span class="sxs-lookup"><span data-stu-id="bfb95-115">This is equivalent to using the command line compiler and referencing the assembly by using the `/link` compiler option.</span></span> <span data-ttu-id="bfb95-116">Das Clientprogramm kann dann Instanzen Ihrer Laufzeitobjekte laden, die als diese Schnittstellen typisiert sind.</span><span class="sxs-lookup"><span data-stu-id="bfb95-116">The client program can then load instances of your runtime objects typed as those interfaces.</span></span> <span data-ttu-id="bfb95-117">Wenn Sie eine neue Version Ihrer Runtime-Assembly mit starkem Namen erstellen, muss das Clientprogramm nicht erneut mit der aktualisierten Runtime-Assembly kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="bfb95-117">If you create a new version of your strong-named runtime assembly, the client program does not have to be recompiled with the updated runtime assembly.</span></span> <span data-ttu-id="bfb95-118">Stattdessen verwendet das Clientprogramm weiterhin die verfügbare Version der Runtime-Assembly und verwendet die eingebetteten Typinformationen für die öffentlichen Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="bfb95-118">Instead, the client program continues to use whichever version of the runtime assembly is available to it, using the embedded type information for the public interfaces.</span></span>  
  
 <span data-ttu-id="bfb95-119">Da die primäre Funktion des Einbettens von Typen die Unterstützung des Einbettens von Typinformationen von COM-Interop-Assemblys ist, gelten die folgenden Einschränkungen, wenn Sie Typinformationen in eine vollständig verwaltete Lösung einbetten:</span><span class="sxs-lookup"><span data-stu-id="bfb95-119">Because the primary function of type embedding is to support embedding of type information from COM interop assemblies, the following limitations apply when you embed type information in a fully managed solution:</span></span>  
  
-   <span data-ttu-id="bfb95-120">Nur die für COM-Interop spezifischen Attribute werden eingebettet; andere Attribute werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="bfb95-120">Only attributes specific to COM interop are embedded; other attributes are ignored.</span></span>  
  
-   <span data-ttu-id="bfb95-121">Wenn ein Typ generische Parameter verwendet, und der Typ des generischen Parameters ein eingebetteter Typ ist, kann dieser Typ nicht über die Grenze einer Assembly hinaus verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bfb95-121">If a type uses generic parameters and the type of the generic parameter is an embedded type, that type cannot be used across an assembly boundary.</span></span> <span data-ttu-id="bfb95-122">Beispiele für das Überschreiten der Grenze einer Assembly umfassen das Aufrufen einer Methode von einer anderen Assembly aus oder das Ableiten eines Typs von einem Typ, der in einer anderen Assembly definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="bfb95-122">Examples of crossing an assembly boundary include calling a method from another assembly or a deriving a type from a type defined in another assembly.</span></span>  
  
-   <span data-ttu-id="bfb95-123">Konstanten werden nicht eingebettet.</span><span class="sxs-lookup"><span data-stu-id="bfb95-123">Constants are not embedded.</span></span>  
  
-   <span data-ttu-id="bfb95-124">Die <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName>-Klasse unterstützt keinen eingebetteten Typ als Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="bfb95-124">The <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName> class does not support an embedded type as a key.</span></span> <span data-ttu-id="bfb95-125">Sie können Ihren eigenen Wörterbuchtyp implementieren, um einen eingebetteten Typ als Schlüssel zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="bfb95-125">You can implement your own dictionary type to support an embedded type as a key.</span></span>  
  
 <span data-ttu-id="bfb95-126">Im Verlauf dieser exemplarischen Vorgehensweise führen Sie folgende Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="bfb95-126">In this walkthrough, you will do the following:</span></span>  
  
-   <span data-ttu-id="bfb95-127">Erstellen Sie eine Assembly mit starkem Namen mit einer öffentlichen Schnittstelle, die Typinformationen enthält, die eingebettet werden können.</span><span class="sxs-lookup"><span data-stu-id="bfb95-127">Create a strong-named assembly that has a public interface that contains type information that can be embedded.</span></span>  
  
-   <span data-ttu-id="bfb95-128">Erstellen Sie eine Runtime-Assembly mit starkem Namen, die diese öffentliche Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="bfb95-128">Create a strong-named runtime assembly that implements that public interface.</span></span>  
  
-   <span data-ttu-id="bfb95-129">Erstellen Sie ein Clientprogramm, das die Typinformationen aus der öffentlichen Schnittstelle einbettet und eine Instanz der Klasse aus der Runtime-Assembly erstellt.</span><span class="sxs-lookup"><span data-stu-id="bfb95-129">Create a client program that embeds the type information from the public interface and creates an instance of the class from the runtime assembly.</span></span>  
  
-   <span data-ttu-id="bfb95-130">Ändern Sie die Runtime-Assembly, und erstellen Sie sie erneut.</span><span class="sxs-lookup"><span data-stu-id="bfb95-130">Modify and rebuild the runtime assembly.</span></span>  
  
-   <span data-ttu-id="bfb95-131">Führen Sie das Clientprogramm aus, um zu prüfen, dass die neue Version der Runtime-Assembly verwendet wird, ohne dass das Clientprogramm erneut kompiliert werden muss.</span><span class="sxs-lookup"><span data-stu-id="bfb95-131">Run the client program to see that the new version of the runtime assembly is being used without having to recompile the client program.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-an-interface"></a><span data-ttu-id="bfb95-132">Erstellen einer Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bfb95-132">Creating an Interface</span></span>  
  
#### <a name="to-create-the-type-equivalence-interface-project"></a><span data-ttu-id="bfb95-133">So erstellen Sie das Schnittstellenprojekt mit Typäquivalenz</span><span class="sxs-lookup"><span data-stu-id="bfb95-133">To create the type equivalence interface project</span></span>  
  
1.  <span data-ttu-id="bfb95-134">Wählen Sie in Visual Studio im Menü **Datei** die Option **Neu** aus, und klicken Sie auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-134">In Visual Studio, on the **File** menu, choose **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="bfb95-135">Überprüfen Sie, ob im Dialogfeld **Neues Projekt** im Bereich **Projekttypen** der Eintrag **Windows** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="bfb95-135">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="bfb95-136">Wählen Sie im Bereich **Vorlagen** die Option **Klassenbibliothek** aus.</span><span class="sxs-lookup"><span data-stu-id="bfb95-136">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="bfb95-137">Geben Sie im Feld **Name** die Bezeichnung `TypeEquivalenceInterface` ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-137">In the **Name** box, type `TypeEquivalenceInterface`, and then click **OK**.</span></span> <span data-ttu-id="bfb95-138">Das neue Projekt wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="bfb95-138">The new project is created.</span></span>  
  
3.  <span data-ttu-id="bfb95-139">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Datei „Class1.cs“, und klicken Sie auf **Umbenennen**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-139">In **Solution Explorer**, right-click the Class1.cs file and click **Rename**.</span></span> <span data-ttu-id="bfb95-140">Benennen Sie die Datei in `ISampleInterface.cs` um, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="bfb95-140">Rename the file to `ISampleInterface.cs` and press ENTER.</span></span> <span data-ttu-id="bfb95-141">Durch Umbenennen der Datei wird die Klasse ebenfalls in `ISampleInterface` umbenannt.</span><span class="sxs-lookup"><span data-stu-id="bfb95-141">Renaming the file will also rename the class to `ISampleInterface`.</span></span> <span data-ttu-id="bfb95-142">Diese Klasse stellt die öffentliche Schnittstelle für die Klasse dar.</span><span class="sxs-lookup"><span data-stu-id="bfb95-142">This class will represent the public interface for the class.</span></span>  
  
4.  <span data-ttu-id="bfb95-143">Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceInterface“, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-143">Right-click the TypeEquivalenceInterface project and click **Properties**.</span></span> <span data-ttu-id="bfb95-144">Klicken Sie auf die Registerkarte **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-144">Click the the **Build** tab.</span></span> <span data-ttu-id="bfb95-145">Legen Sie den Ausgabepfad auf einen gültigen Speicherort auf dem Entwicklungscomputer fest, z.B. auf `C:\TypeEquivalenceSample`.</span><span class="sxs-lookup"><span data-stu-id="bfb95-145">Set the output path to a valid location on your development computer, such as `C:\TypeEquivalenceSample`.</span></span> <span data-ttu-id="bfb95-146">Dieser Speicherort wird auch in einem späteren Schritt in dieser exemplarischen Vorgehensweise verwendet.</span><span class="sxs-lookup"><span data-stu-id="bfb95-146">This location will also be used in a later step in this walkthrough.</span></span>  
  
5.  <span data-ttu-id="bfb95-147">Klicken Sie auf die Schaltfläche **Signierung**, während Sie noch die Projekteigenschaften bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="bfb95-147">While still editing the project properties, click the **Signing** tab.</span></span> <span data-ttu-id="bfb95-148">Wählen Sie die Option **Assembly signieren** aus.</span><span class="sxs-lookup"><span data-stu-id="bfb95-148">Select the **Sign the assembly** option.</span></span> <span data-ttu-id="bfb95-149">Klicken Sie in der Liste **Schlüsseldatei mit starkem Namen auswählen** auf **<Neu...>**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-149">In the **Choose a strong name key file** list, click **<New...>**.</span></span> <span data-ttu-id="bfb95-150">Geben Sie im Feld **Schlüsseldateiname** `key.snk`ein.</span><span class="sxs-lookup"><span data-stu-id="bfb95-150">In the **Key file name** box, type `key.snk`.</span></span> <span data-ttu-id="bfb95-151">Deaktivieren Sie das Kontrollkästchen **Schlüsseldatei mit Kennwort schützen**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-151">Clear the **Protect my key file with a password** check box.</span></span> <span data-ttu-id="bfb95-152">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-152">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="bfb95-153">Öffnen Sie die Datei „ISampleInterface.cs“.</span><span class="sxs-lookup"><span data-stu-id="bfb95-153">Open the ISampleInterface.cs file.</span></span> <span data-ttu-id="bfb95-154">Fügen Sie den folgenden Code zur Klasse „ISampleInterface“ hinzu, um die ISampleInterface-Schnittstelle zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bfb95-154">Add the following code to the ISampleInterface class file to create the ISampleInterface interface.</span></span>  
  
    ```csharp  
    using System;  
    using System.Runtime.InteropServices;  
  
    namespace TypeEquivalenceInterface  
    {  
        [ComImport]  
        [Guid("8DA56996-A151-4136-B474-32784559F6DF")]  
        public interface ISampleInterface  
        {  
            void GetUserInput();  
            string UserInput { get; }  
        }  
    }  
    ```  
  
7.  <span data-ttu-id="bfb95-155">Klicken Sie im Menü **Extras** auf den Befehl **GUID erstellen**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-155">On the **Tools** menu, click **Create Guid**.</span></span> <span data-ttu-id="bfb95-156">Klicken Sie im Dialogfeld **GUID erstellen** auf **Registrierungsformat** und anschließend auf **Kopieren**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-156">In the **Create GUID** dialog box, click **Registry Format** and then click **Copy**.</span></span> <span data-ttu-id="bfb95-157">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-157">Click **Exit**.</span></span>  
  
8.  <span data-ttu-id="bfb95-158">Löschen Sie die Beispiel-GUID im Attribut `Guid`, und fügen Sie die GUID ein, die Sie aus dem Dialogfeld **GUID erstellen** kopiert haben.</span><span class="sxs-lookup"><span data-stu-id="bfb95-158">In the `Guid` attribute, delete the sample GUID and paste in the GUID that you copied from the **Create GUID** dialog box.</span></span> <span data-ttu-id="bfb95-159">Entfernen Sie die geschweiften Klammern ({}) aus der kopierten GUID.</span><span class="sxs-lookup"><span data-stu-id="bfb95-159">Remove the braces ({}) from the copied GUID.</span></span>  
  
9. <span data-ttu-id="bfb95-160">Erweitern Sie im **Projektmappen-Explorer** den Ordner **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-160">In **Solution Explorer**, expand the **Properties** folder.</span></span> <span data-ttu-id="bfb95-161">Doppelklicken Sie auf die Datei „AssemblyInfo.cs“.</span><span class="sxs-lookup"><span data-stu-id="bfb95-161">Double-click the AssemblyInfo.cs file.</span></span> <span data-ttu-id="bfb95-162">Fügen Sie folgendes Attribut zur Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="bfb95-162">Add the following attribute to the file.</span></span>  
  
    ```csharp  
    [assembly: ImportedFromTypeLib("")]  
    ```  
  
     <span data-ttu-id="bfb95-163">Speichern Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="bfb95-163">Save the file.</span></span>  
  
10. <span data-ttu-id="bfb95-164">Speichern Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="bfb95-164">Save the project.</span></span>  
  
11. <span data-ttu-id="bfb95-165">Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceInterface“, und klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-165">Right-click the TypeEquivalenceInterface project and click **Build**.</span></span> <span data-ttu-id="bfb95-166">Die DLL-Datei der Klassenbibliothek wird kompiliert und im angegebenen Buildausgabepfad gespeichert (z.B. C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="bfb95-166">The class library .dll file is compiled and saved to the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="creating-a-runtime-class"></a><span data-ttu-id="bfb95-167">Erstellen einer Runtime-Klasse</span><span class="sxs-lookup"><span data-stu-id="bfb95-167">Creating a Runtime Class</span></span>  
  
#### <a name="to-create-the-type-equivalence-runtime-project"></a><span data-ttu-id="bfb95-168">So erstellen Sie das Runtime-Projekt mit Typäquivalenz</span><span class="sxs-lookup"><span data-stu-id="bfb95-168">To create the type equivalence runtime project</span></span>  
  
1.  <span data-ttu-id="bfb95-169">Zeigen Sie in Visual Studio im Menü **Datei** auf **Neu**, und klicken Sie auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-169">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="bfb95-170">Überprüfen Sie, ob im Dialogfeld **Neues Projekt** im Bereich **Projekttypen** der Eintrag **Windows** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="bfb95-170">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="bfb95-171">Wählen Sie im Bereich **Vorlagen** die Option **Klassenbibliothek** aus.</span><span class="sxs-lookup"><span data-stu-id="bfb95-171">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="bfb95-172">Geben Sie im Feld **Name** die Bezeichnung `TypeEquivalenceRuntime` ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-172">In the **Name** box, type `TypeEquivalenceRuntime`, and then click **OK**.</span></span> <span data-ttu-id="bfb95-173">Das neue Projekt wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="bfb95-173">The new project is created.</span></span>  
  
3.  <span data-ttu-id="bfb95-174">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Datei „Class1.cs“, und klicken Sie auf **Umbenennen**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-174">In **Solution Explorer**, right-click the Class1.cs file and click **Rename**.</span></span> <span data-ttu-id="bfb95-175">Benennen Sie die Datei in `SampleClass.cs` um, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="bfb95-175">Rename the file to `SampleClass.cs` and press ENTER.</span></span> <span data-ttu-id="bfb95-176">Durch Umbenennen der Datei wird die Klasse ebenfalls in `SampleClass` umbenannt.</span><span class="sxs-lookup"><span data-stu-id="bfb95-176">Renaming the file also renames the class to `SampleClass`.</span></span> <span data-ttu-id="bfb95-177">Diese Klasse implementiert die `ISampleInterface`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="bfb95-177">This class will implement the `ISampleInterface` interface.</span></span>  
  
4.  <span data-ttu-id="bfb95-178">Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceRuntime“, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-178">Right-click the TypeEquivalenceRuntime project and click **Properties**.</span></span> <span data-ttu-id="bfb95-179">Klicken Sie auf die Registerkarte **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-179">Click the **Build** tab.</span></span> <span data-ttu-id="bfb95-180">Legen Sie den Ausgabepfad auf denselben Speicherort fest, den Sie im Projekt „TypeEquivalenceInterface“ verwendet haben, z.B. auf `C:\TypeEquivalenceSample`.</span><span class="sxs-lookup"><span data-stu-id="bfb95-180">Set the output path to the same location you used in the TypeEquivalenceInterface project, for example, `C:\TypeEquivalenceSample`.</span></span>  
  
5.  <span data-ttu-id="bfb95-181">Klicken Sie auf die Schaltfläche **Signierung**, während Sie noch die Projekteigenschaften bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="bfb95-181">While still editing the project properties, click the **Signing** tab.</span></span> <span data-ttu-id="bfb95-182">Wählen Sie die Option **Assembly signieren** aus.</span><span class="sxs-lookup"><span data-stu-id="bfb95-182">Select the **Sign the assembly** option.</span></span> <span data-ttu-id="bfb95-183">Klicken Sie in der Liste **Schlüsseldatei mit starkem Namen auswählen** auf **<Neu...>**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-183">In the **Choose a strong name key file** list, click **<New...>**.</span></span> <span data-ttu-id="bfb95-184">Geben Sie im Feld **Schlüsseldateiname** `key.snk`ein.</span><span class="sxs-lookup"><span data-stu-id="bfb95-184">In the **Key file name** box, type `key.snk`.</span></span> <span data-ttu-id="bfb95-185">Deaktivieren Sie das Kontrollkästchen **Schlüsseldatei mit Kennwort schützen**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-185">Clear the **Protect my key file with a password** check box.</span></span> <span data-ttu-id="bfb95-186">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-186">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="bfb95-187">Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceRuntime“, und klicken Sie auf **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-187">Right-click the TypeEquivalenceRuntime project and click **Add Reference**.</span></span> <span data-ttu-id="bfb95-188">Klicken Sie auf die Registerkarte **Durchsuchen**, und navigieren Sie zum Ausgabeordner für den Pfad.</span><span class="sxs-lookup"><span data-stu-id="bfb95-188">Click the **Browse** tab and browse to the output path folder.</span></span> <span data-ttu-id="bfb95-189">Wählen Sie die Datei „TypeEquivalenceInterface.dll“ aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-189">Select the TypeEquivalenceInterface.dll file and click **OK**.</span></span>  
  
7.  <span data-ttu-id="bfb95-190">Erweitern Sie im **Projektmappen-Explorer** den Ordner **Verweise**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-190">In **Solution Explorer**, expand the **References** folder.</span></span> <span data-ttu-id="bfb95-191">Wählen Sie den Verweis „TypeEquivalenceInterface“ aus.</span><span class="sxs-lookup"><span data-stu-id="bfb95-191">Select the TypeEquivalenceInterface reference.</span></span> <span data-ttu-id="bfb95-192">Legen Sie im Eigenschaftenfenster für den Verweis „TypeEquivalenceInterface“ die Eigenschaft **Spezifische Version** auf **False** fest.</span><span class="sxs-lookup"><span data-stu-id="bfb95-192">In the Properties window for the TypeEquivalenceInterface reference, set the **Specific Version** property to **False**.</span></span>  
  
8.  <span data-ttu-id="bfb95-193">Fügen Sie den folgenden Code zur Klassendatei „SampleClass“ hinzu, um die Klasse SampleClass zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bfb95-193">Add the following code to the SampleClass class file to create the SampleClass class.</span></span>  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using TypeEquivalenceInterface;  
  
    namespace TypeEquivalenceRuntime  
    {  
        public class SampleClass : ISampleInterface  
        {  
            private string p_UserInput;  
            public string UserInput { get { return p_UserInput; } }  
  
            public void GetUserInput()  
            {  
                Console.WriteLine("Please enter a value:");  
                p_UserInput = Console.ReadLine();  
            }  
        }  
    )  
    ```  
  
9. <span data-ttu-id="bfb95-194">Speichern Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="bfb95-194">Save the project.</span></span>  
  
10. <span data-ttu-id="bfb95-195">Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceRuntime“, und klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-195">Right-click the TypeEquivalenceRuntime project and click **Build**.</span></span> <span data-ttu-id="bfb95-196">Die DLL-Datei der Klassenbibliothek wird kompiliert und im angegebenen Buildausgabepfad gespeichert (z.B. C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="bfb95-196">The class library .dll file is compiled and saved to the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="creating-a-client-project"></a><span data-ttu-id="bfb95-197">Erstellen eines Clientprojekts</span><span class="sxs-lookup"><span data-stu-id="bfb95-197">Creating a Client Project</span></span>  
  
#### <a name="to-create-the-type-equivalence-client-project"></a><span data-ttu-id="bfb95-198">So erstellen Sie das Clientprojekt mit Typäquivalenz</span><span class="sxs-lookup"><span data-stu-id="bfb95-198">To create the type equivalence client project</span></span>  
  
1.  <span data-ttu-id="bfb95-199">Zeigen Sie in Visual Studio im Menü **Datei** auf **Neu**, und klicken Sie auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-199">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="bfb95-200">Überprüfen Sie, ob im Dialogfeld **Neues Projekt** im Bereich **Projekttypen** der Eintrag **Windows** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="bfb95-200">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="bfb95-201">Wählen Sie im Bereich **Vorlagen** die Option **Konsolenanwendung** aus.</span><span class="sxs-lookup"><span data-stu-id="bfb95-201">Select **Console Application** in the **Templates** pane.</span></span> <span data-ttu-id="bfb95-202">Geben Sie im Feld **Name** die Bezeichnung `TypeEquivalenceClient` ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-202">In the **Name** box, type `TypeEquivalenceClient`, and then click **OK**.</span></span> <span data-ttu-id="bfb95-203">Das neue Projekt wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="bfb95-203">The new project is created.</span></span>  
  
3.  <span data-ttu-id="bfb95-204">Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceClient“, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-204">Right-click the TypeEquivalenceClient project and click **Properties**.</span></span> <span data-ttu-id="bfb95-205">Klicken Sie auf die Registerkarte **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-205">Click the **Build** tab.</span></span> <span data-ttu-id="bfb95-206">Legen Sie den Ausgabepfad auf denselben Speicherort fest, den Sie im Projekt „TypeEquivalenceInterface“ verwendet haben, z.B. auf `C:\TypeEquivalenceSample`.</span><span class="sxs-lookup"><span data-stu-id="bfb95-206">Set the output path to the same location you used in the TypeEquivalenceInterface project, for example, `C:\TypeEquivalenceSample`.</span></span>  
  
4.  <span data-ttu-id="bfb95-207">Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceClient“, und klicken Sie auf **Verweis Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-207">Right-click the TypeEquivalenceClient project and click **Add Reference**.</span></span> <span data-ttu-id="bfb95-208">Klicken Sie auf die Registerkarte **Durchsuchen**, und navigieren Sie zum Ausgabeordner für den Pfad.</span><span class="sxs-lookup"><span data-stu-id="bfb95-208">Click the **Browse** tab and browse to the output path folder.</span></span> <span data-ttu-id="bfb95-209">Wählen Sie die Datei „TypeEquivalenceInterface.dll“ aus (nicht „TypeEquivalenceRuntime.dll“), und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-209">Select the TypeEquivalenceInterface.dll file (not the TypeEquivalenceRuntime.dll) and click **OK**.</span></span>  
  
5.  <span data-ttu-id="bfb95-210">Erweitern Sie im **Projektmappen-Explorer** den Ordner **Verweise**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-210">In **Solution Explorer**, expand the **References** folder.</span></span> <span data-ttu-id="bfb95-211">Wählen Sie den Verweis „TypeEquivalenceInterface“ aus.</span><span class="sxs-lookup"><span data-stu-id="bfb95-211">Select the TypeEquivalenceInterface reference.</span></span> <span data-ttu-id="bfb95-212">Legen Sie im Eigenschaftenfenster für den Verweis „TypeEquivalenceInterface“ die Eigenschaft **Einbetten von Interop-Typen** auf **True** fest.</span><span class="sxs-lookup"><span data-stu-id="bfb95-212">In the Properties window for the TypeEquivalenceInterface reference, set the **Embed Interop Types** property to **True**.</span></span>  
  
6.  <span data-ttu-id="bfb95-213">Fügen Sie folgenden Code zur Datei „Program.cs“ hinzu, um das Clientprogramm zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bfb95-213">Add the following code to the Program.cs file to create the client program.</span></span>  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using TypeEquivalenceInterface;  
    using System.Reflection;  
  
    namespace TypeEquivalenceClient  
    {  
        class Program  
        {  
            static void Main(string[] args)  
            {  
                Assembly sampleAssembly = Assembly.Load("TypeEquivalenceRuntime");  
                ISampleInterface sampleClass =   
                    (ISampleInterface)sampleAssembly.CreateInstance("TypeEquivalenceRuntime.SampleClass");  
                sampleClass.GetUserInput();  
                Console.WriteLine(sampleClass.UserInput);  
                Console.WriteLine(sampleAssembly.GetName().Version.ToString());  
                Console.ReadLine();  
            }  
        }  
    }  
    ```  
  
7.  <span data-ttu-id="bfb95-214">Drücken Sie STRG+F5, um das Programm zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="bfb95-214">Press CTRL+F5 to build and run the program.</span></span>  
  
## <a name="modifying-the-interface"></a><span data-ttu-id="bfb95-215">Ändern der Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bfb95-215">Modifying the Interface</span></span>  
  
#### <a name="to-modify-the-interface"></a><span data-ttu-id="bfb95-216">So ändern Sie die Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bfb95-216">To modify the interface</span></span>  
  
1.  <span data-ttu-id="bfb95-217">Zeigen Sie in Visual Studio im Menü **Datei** auf **Öffnen**, und klicken Sie auf **Projekt/Projektmappe**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-217">In Visual Studio, on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
2.  <span data-ttu-id="bfb95-218">Klicken Sie im Dialogfeld **Projekt öffnen** mit der rechten Maustaste auf das Projekt „TypeEquivalenceInterface“, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-218">In the **Open Project** dialog box, right-click the TypeEquivalenceInterface project, and then click **Properties**.</span></span> <span data-ttu-id="bfb95-219">Klicken Sie auf die Registerkarte **Anwendung** .</span><span class="sxs-lookup"><span data-stu-id="bfb95-219">Click the **Application** tab.</span></span> <span data-ttu-id="bfb95-220">Klicken Sie auf die Schaltfläche **Assemblyinformationen**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-220">Click the **Assembly Information** button.</span></span> <span data-ttu-id="bfb95-221">Ändern Sie die Werte der **Assemblyversion** und der **Dateiversion** in `2.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="bfb95-221">Change the **Assembly Version** and **File Version** values to `2.0.0.0`.</span></span>  
  
3.  <span data-ttu-id="bfb95-222">Öffnen Sie die Datei „SampleInterface.cs“.</span><span class="sxs-lookup"><span data-stu-id="bfb95-222">Open the SampleInterface.cs file.</span></span> <span data-ttu-id="bfb95-223">Fügen Sie der ISampleInterface-Schnittstelle die folgende Codezeile hinzu.</span><span class="sxs-lookup"><span data-stu-id="bfb95-223">Add the following line of code to the ISampleInterface interface.</span></span>  
  
    ```csharp  
    DateTime GetDate();  
    ```  
  
     <span data-ttu-id="bfb95-224">Speichern Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="bfb95-224">Save the file.</span></span>  
  
4.  <span data-ttu-id="bfb95-225">Speichern Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="bfb95-225">Save the project.</span></span>  
  
5.  <span data-ttu-id="bfb95-226">Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceInterface“, und klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-226">Right-click the TypeEquivalenceInterface project and click **Build**.</span></span> <span data-ttu-id="bfb95-227">Eine neue Version der DLL-Datei der Klassenbibliothek wird kompiliert und im angegebenen Buildausgabepfad gespeichert (z.B. C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="bfb95-227">A new version of the class library .dll file is compiled and saved in the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="modifying-the-runtime-class"></a><span data-ttu-id="bfb95-228">Ändern der Runtime-Klasse</span><span class="sxs-lookup"><span data-stu-id="bfb95-228">Modifying the Runtime Class</span></span>  
  
#### <a name="to-modify-the-runtime-class"></a><span data-ttu-id="bfb95-229">So ändern Sie die Runtime-Klasse</span><span class="sxs-lookup"><span data-stu-id="bfb95-229">To modify the runtime class</span></span>  
  
1.  <span data-ttu-id="bfb95-230">Zeigen Sie in Visual Studio im Menü **Datei** auf **Öffnen**, und klicken Sie auf **Projekt/Projektmappe**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-230">In Visual Studio, on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
2.  <span data-ttu-id="bfb95-231">Klicken Sie im Dialogfeld **Projekt öffnen** mit der rechten Maustaste auf das Projekt „TypeEquivalenceRuntime“, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-231">In the **Open Project** dialog box, right-click the TypeEquivalenceRuntime project and click **Properties**.</span></span> <span data-ttu-id="bfb95-232">Klicken Sie auf die Registerkarte **Anwendung** .</span><span class="sxs-lookup"><span data-stu-id="bfb95-232">Click the **Application** tab.</span></span> <span data-ttu-id="bfb95-233">Klicken Sie auf die Schaltfläche **Assemblyinformationen**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-233">Click the **Assembly Information** button.</span></span> <span data-ttu-id="bfb95-234">Ändern Sie die Werte der **Assemblyversion** und der **Dateiversion** in `2.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="bfb95-234">Change the **Assembly Version** and **File Version** values to `2.0.0.0`.</span></span>  
  
3.  <span data-ttu-id="bfb95-235">Öffnen Sie die Datei „SampleClass.cs“.</span><span class="sxs-lookup"><span data-stu-id="bfb95-235">Open the SampleClass.cs file.</span></span> <span data-ttu-id="bfb95-236">Fügen Sie folgenden Codezeilen zur Klasse „SampleClass“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="bfb95-236">Add the following lines of code to the SampleClass class.</span></span>  
  
    ```csharp  
    public DateTime GetDate()  
    {  
        return DateTime.Now;  
    }  
    ```  
  
     <span data-ttu-id="bfb95-237">Speichern Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="bfb95-237">Save the file.</span></span>  
  
4.  <span data-ttu-id="bfb95-238">Speichern Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="bfb95-238">Save the project.</span></span>  
  
5.  <span data-ttu-id="bfb95-239">Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceRuntime“, und klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="bfb95-239">Right-click the TypeEquivalenceRuntime project and click **Build**.</span></span> <span data-ttu-id="bfb95-240">Eine aktualisierte Version der DLL-Datei der Klassenbibliothek wird kompiliert und im vorher angegebenen Buildausgabepfad gespeichert (z.B. C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="bfb95-240">An updated version of the class library .dll file is compiled and saved in the previously specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
6.  <span data-ttu-id="bfb95-241">Öffnen Sie im Datei-Explorer den Ordner mit dem Ausgabepfad (z.B. C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="bfb95-241">In File Explorer, open the output path folder (for example, C:\TypeEquivalenceSample).</span></span> <span data-ttu-id="bfb95-242">Doppelklicken Sie auf die Datei „TypeEquivalenceClient.exe“, um das Programm auszuführen.</span><span class="sxs-lookup"><span data-stu-id="bfb95-242">Double-click the TypeEquivalenceClient.exe to run the program.</span></span> <span data-ttu-id="bfb95-243">Das Programm reflektiert die neue Version der TypeEquivalenceRuntime-Assembly, ohne dass sie erneut kompiliert werden muss.</span><span class="sxs-lookup"><span data-stu-id="bfb95-243">The program will reflect the new version of the TypeEquivalenceRuntime assembly without having been recompiled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfb95-244">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bfb95-244">See Also</span></span>  
 <span data-ttu-id="bfb95-245">[/link (C#-Compileroptionen)](../../../../csharp/language-reference/compiler-options/link-compiler-option.md) </span><span class="sxs-lookup"><span data-stu-id="bfb95-245">[/link (C# Compiler Options)](../../../../csharp/language-reference/compiler-options/link-compiler-option.md) </span></span>  
 <span data-ttu-id="bfb95-246">[C#-Programmierhandbuch](../../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="bfb95-246">[C# Programming Guide](../../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="bfb95-247">[Programmieren mit Assemblys](../../../../framework/app-domains/programming-with-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="bfb95-247">[Programming with Assemblies](../../../../framework/app-domains/programming-with-assemblies.md) </span></span>  
 [<span data-ttu-id="bfb95-248">Assemblys und der globale Assemblycache (C#)</span><span class="sxs-lookup"><span data-stu-id="bfb95-248">Assemblies and the Global Assembly Cache (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)

