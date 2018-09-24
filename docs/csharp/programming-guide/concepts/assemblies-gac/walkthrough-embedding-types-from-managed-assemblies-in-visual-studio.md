---
title: 'Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys in Visual Studio (C#)'
ms.date: 07/20/2015
ms.assetid: 55ed13c9-c5bb-4bc2-bcd8-0587eb568864
ms.openlocfilehash: 1900c62d1ebaf611f141f8f1bdf95f8d11f82140
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46004324"
---
# <a name="walkthrough-embedding-types-from-managed-assemblies-in-visual-studio-c"></a><span data-ttu-id="a1b24-102">Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys in Visual Studio (C#)</span><span class="sxs-lookup"><span data-stu-id="a1b24-102">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (C#)</span></span>
<span data-ttu-id="a1b24-103">Wenn Sie Typinformationen von einer verwalteten Assembly mit starkem Namen einbetten, können Sie Typen in einer Anwendung lose koppeln, um versionsunabhängig zu werden.</span><span class="sxs-lookup"><span data-stu-id="a1b24-103">If you embed type information from a strong-named managed assembly, you can loosely couple types in an application to achieve version independence.</span></span> <span data-ttu-id="a1b24-104">Ihr Programm kann daher für Typen aus unterschiedlichen Versionen einer verwalteten Bibliothek geschrieben werden; eine erneute Kompilierung für jede Version ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a1b24-104">That is, your program can be written to use types from multiple versions of a managed library without having to be recompiled for each version.</span></span>  
  
 <span data-ttu-id="a1b24-105">Das Einbetten von Typen wird häufig mit COM-Interop verwendet, z.B. mit einer Anwendung, die Automatisierungsobjekte von Microsoft Office verwendet.</span><span class="sxs-lookup"><span data-stu-id="a1b24-105">Type embedding is frequently used with COM interop, such as an application that uses automation objects from Microsoft Office.</span></span> <span data-ttu-id="a1b24-106">Das Einbetten von Typinformationen lässt zu, dass derselbe Build eines Programms mit unterschiedlichen Versionen von Microsoft Office auf verschiedenen Computern verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="a1b24-106">Embedding type information enables the same build of a program to work with different versions of Microsoft Office on different computers.</span></span> <span data-ttu-id="a1b24-107">Sie können das Einbetten von Typen jedoch auch mit einer vollständig verwalteten Anwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="a1b24-107">However, you can also use type embedding with a fully managed solution.</span></span>  
  
 <span data-ttu-id="a1b24-108">Typinformationen können von einer Assembly aus eingebettet werden, die die folgenden Merkmale aufweist:</span><span class="sxs-lookup"><span data-stu-id="a1b24-108">Type information can be embedded from an assembly that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="a1b24-109">Die Assembly macht mindestens eine öffentliche Schnittstelle verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a1b24-109">The assembly exposes at least one public interface.</span></span>  
  
-   <span data-ttu-id="a1b24-110">Die eingebetteten Schnittstellen werden mit einem `ComImport`-Attribut und einem `Guid`-Attribut (und einer eindeutigen GUID) kommentiert.</span><span class="sxs-lookup"><span data-stu-id="a1b24-110">The embedded interfaces are annotated with a `ComImport` attribute and a `Guid` attribute (and a unique GUID).</span></span>  
  
-   <span data-ttu-id="a1b24-111">Die Assembly wird mit dem `ImportedFromTypeLib`-Attribut oder dem `PrimaryInteropAssembly`-Attribut und einem `Guid`-Attribut auf Assemblyebene kommentiert.</span><span class="sxs-lookup"><span data-stu-id="a1b24-111">The assembly is annotated with the `ImportedFromTypeLib` attribute or the `PrimaryInteropAssembly` attribute, and an assembly-level `Guid` attribute.</span></span> <span data-ttu-id="a1b24-112">(Standardmäßig enthalten Visual C#-Projektvorlagen ein `Guid`-Attribut auf Assemblyebene.)</span><span class="sxs-lookup"><span data-stu-id="a1b24-112">(By default, Visual C# project templates include an assembly-level `Guid` attribute.)</span></span>  
  
 <span data-ttu-id="a1b24-113">Nachdem Sie die öffentlichen Schnittstellen angegeben haben, die eingebettet werden können, können Sie Laufzeitklassen erstellen, die diese Schnittstellen implementieren.</span><span class="sxs-lookup"><span data-stu-id="a1b24-113">After you have specified the public interfaces that can be embedded, you can create runtime classes that implement those interfaces.</span></span> <span data-ttu-id="a1b24-114">Ein Clientprogramm kann dann die Typinformationen für diese Schnittstellen zur Entwurfszeit einbetten, indem auf die Assembly verwiesen wird, die die öffentlichen Schnittstellen enthält und die Eigenschaft `Embed Interop Types` des Verweises auf `True` festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="a1b24-114">A client program can then embed the type information for those interfaces at design time by referencing the assembly that contains the public interfaces and setting the `Embed Interop Types` property of the reference to `True`.</span></span> <span data-ttu-id="a1b24-115">Dies entspricht dem Verwenden des Befehlszeilencompilers und Verweisen auf die Assembly mit der Compileroption `/link`.</span><span class="sxs-lookup"><span data-stu-id="a1b24-115">This is equivalent to using the command line compiler and referencing the assembly by using the `/link` compiler option.</span></span> <span data-ttu-id="a1b24-116">Das Clientprogramm kann dann Instanzen Ihrer Laufzeitobjekte laden, die als diese Schnittstellen typisiert sind.</span><span class="sxs-lookup"><span data-stu-id="a1b24-116">The client program can then load instances of your runtime objects typed as those interfaces.</span></span> <span data-ttu-id="a1b24-117">Wenn Sie eine neue Version Ihrer Runtime-Assembly mit starkem Namen erstellen, muss das Clientprogramm nicht erneut mit der aktualisierten Runtime-Assembly kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="a1b24-117">If you create a new version of your strong-named runtime assembly, the client program does not have to be recompiled with the updated runtime assembly.</span></span> <span data-ttu-id="a1b24-118">Stattdessen verwendet das Clientprogramm weiterhin die verfügbare Version der Runtime-Assembly und verwendet die eingebetteten Typinformationen für die öffentlichen Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="a1b24-118">Instead, the client program continues to use whichever version of the runtime assembly is available to it, using the embedded type information for the public interfaces.</span></span>  
  
 <span data-ttu-id="a1b24-119">Da die primäre Funktion des Einbettens von Typen die Unterstützung des Einbettens von Typinformationen von COM-Interop-Assemblys ist, gelten die folgenden Einschränkungen, wenn Sie Typinformationen in eine vollständig verwaltete Lösung einbetten:</span><span class="sxs-lookup"><span data-stu-id="a1b24-119">Because the primary function of type embedding is to support embedding of type information from COM interop assemblies, the following limitations apply when you embed type information in a fully managed solution:</span></span>  
  
-   <span data-ttu-id="a1b24-120">Nur die für COM-Interop spezifischen Attribute werden eingebettet; andere Attribute werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a1b24-120">Only attributes specific to COM interop are embedded; other attributes are ignored.</span></span>  
  
-   <span data-ttu-id="a1b24-121">Wenn ein Typ generische Parameter verwendet, und der Typ des generischen Parameters ein eingebetteter Typ ist, kann dieser Typ nicht über die Grenze einer Assembly hinaus verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a1b24-121">If a type uses generic parameters and the type of the generic parameter is an embedded type, that type cannot be used across an assembly boundary.</span></span> <span data-ttu-id="a1b24-122">Beispiele für das Überschreiten der Grenze einer Assembly umfassen das Aufrufen einer Methode von einer anderen Assembly aus oder das Ableiten eines Typs von einem Typ, der in einer anderen Assembly definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="a1b24-122">Examples of crossing an assembly boundary include calling a method from another assembly or a deriving a type from a type defined in another assembly.</span></span>  
  
-   <span data-ttu-id="a1b24-123">Konstanten werden nicht eingebettet.</span><span class="sxs-lookup"><span data-stu-id="a1b24-123">Constants are not embedded.</span></span>  
  
-   <span data-ttu-id="a1b24-124">Die <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>-Klasse unterstützt keinen eingebetteten Typ als Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="a1b24-124">The <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> class does not support an embedded type as a key.</span></span> <span data-ttu-id="a1b24-125">Sie können Ihren eigenen Wörterbuchtyp implementieren, um einen eingebetteten Typ als Schlüssel zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a1b24-125">You can implement your own dictionary type to support an embedded type as a key.</span></span>  
  
 <span data-ttu-id="a1b24-126">Im Verlauf dieser exemplarischen Vorgehensweise führen Sie folgende Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="a1b24-126">In this walkthrough, you will do the following:</span></span>  
  
-   <span data-ttu-id="a1b24-127">Erstellen Sie eine Assembly mit starkem Namen mit einer öffentlichen Schnittstelle, die Typinformationen enthält, die eingebettet werden können.</span><span class="sxs-lookup"><span data-stu-id="a1b24-127">Create a strong-named assembly that has a public interface that contains type information that can be embedded.</span></span>  
  
-   <span data-ttu-id="a1b24-128">Erstellen Sie eine Runtime-Assembly mit starkem Namen, die diese öffentliche Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="a1b24-128">Create a strong-named runtime assembly that implements that public interface.</span></span>  
  
-   <span data-ttu-id="a1b24-129">Erstellen Sie ein Clientprogramm, das die Typinformationen aus der öffentlichen Schnittstelle einbettet und eine Instanz der Klasse aus der Runtime-Assembly erstellt.</span><span class="sxs-lookup"><span data-stu-id="a1b24-129">Create a client program that embeds the type information from the public interface and creates an instance of the class from the runtime assembly.</span></span>  
  
-   <span data-ttu-id="a1b24-130">Ändern Sie die Runtime-Assembly, und erstellen Sie sie erneut.</span><span class="sxs-lookup"><span data-stu-id="a1b24-130">Modify and rebuild the runtime assembly.</span></span>  
  
-   <span data-ttu-id="a1b24-131">Führen Sie das Clientprogramm aus, um zu prüfen, dass die neue Version der Runtime-Assembly verwendet wird, ohne dass das Clientprogramm erneut kompiliert werden muss.</span><span class="sxs-lookup"><span data-stu-id="a1b24-131">Run the client program to see that the new version of the runtime assembly is being used without having to recompile the client program.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-an-interface"></a><span data-ttu-id="a1b24-132">Erstellen einer Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a1b24-132">Creating an Interface</span></span>  
  
#### <a name="to-create-the-type-equivalence-interface-project"></a><span data-ttu-id="a1b24-133">So erstellen Sie das Schnittstellenprojekt mit Typäquivalenz</span><span class="sxs-lookup"><span data-stu-id="a1b24-133">To create the type equivalence interface project</span></span>  
  
1.  <span data-ttu-id="a1b24-134">Wählen Sie in Visual Studio im Menü **Datei** die Option **Neu** aus, und klicken Sie auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="a1b24-134">In Visual Studio, on the **File** menu, choose **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="a1b24-135">Überprüfen Sie, ob im Dialogfeld **Neues Projekt** im Bereich **Projekttypen** der Eintrag **Windows** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="a1b24-135">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="a1b24-136">Wählen Sie im Bereich **Vorlagen** die Option **Klassenbibliothek** aus.</span><span class="sxs-lookup"><span data-stu-id="a1b24-136">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="a1b24-137">Geben Sie im Feld **Name** die Bezeichnung `TypeEquivalenceInterface` ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a1b24-137">In the **Name** box, type `TypeEquivalenceInterface`, and then click **OK**.</span></span> <span data-ttu-id="a1b24-138">Das neue Projekt wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="a1b24-138">The new project is created.</span></span>  
  
3.  <span data-ttu-id="a1b24-139">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Datei „Class1.cs“, und klicken Sie auf **Umbenennen**.</span><span class="sxs-lookup"><span data-stu-id="a1b24-139">In **Solution Explorer**, right-click the Class1.cs file and click **Rename**.</span></span> <span data-ttu-id="a1b24-140">Benennen Sie die Datei in `ISampleInterface.cs` um, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="a1b24-140">Rename the file to `ISampleInterface.cs` and press ENTER.</span></span> <span data-ttu-id="a1b24-141">Durch Umbenennen der Datei wird die Klasse ebenfalls in `ISampleInterface` umbenannt.</span><span class="sxs-lookup"><span data-stu-id="a1b24-141">Renaming the file will also rename the class to `ISampleInterface`.</span></span> <span data-ttu-id="a1b24-142">Diese Klasse stellt die öffentliche Schnittstelle für die Klasse dar.</span><span class="sxs-lookup"><span data-stu-id="a1b24-142">This class will represent the public interface for the class.</span></span>  
  
4.  <span data-ttu-id="a1b24-143">Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceInterface“, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="a1b24-143">Right-click the TypeEquivalenceInterface project and click **Properties**.</span></span> <span data-ttu-id="a1b24-144">Klicken Sie auf die Registerkarte **Erstellen**. Legen Sie den Ausgabepfad auf einen gültigen Speicherort auf dem Entwicklungscomputer fest, z.B. auf `C:\TypeEquivalenceSample`.</span><span class="sxs-lookup"><span data-stu-id="a1b24-144">Click the **Build** tab. Set the output path to a valid location on your development computer, such as `C:\TypeEquivalenceSample`.</span></span> <span data-ttu-id="a1b24-145">Dieser Speicherort wird auch in einem späteren Schritt in dieser exemplarischen Vorgehensweise verwendet.</span><span class="sxs-lookup"><span data-stu-id="a1b24-145">This location will also be used in a later step in this walkthrough.</span></span>  
  
5.  <span data-ttu-id="a1b24-146">Klicken Sie auf die Schaltfläche **Signierung**, während Sie noch die Projekteigenschaften bearbeiten. Wählen Sie die Option **Assembly signieren** aus.</span><span class="sxs-lookup"><span data-stu-id="a1b24-146">While still editing the project properties, click the **Signing** tab. Select the **Sign the assembly** option.</span></span> <span data-ttu-id="a1b24-147">Klicken Sie in der Liste **Schlüsseldatei mit starkem Namen auswählen** auf **<Neu...>**.</span><span class="sxs-lookup"><span data-stu-id="a1b24-147">In the **Choose a strong name key file** list, click **<New...>**.</span></span> <span data-ttu-id="a1b24-148">Geben Sie im Feld **Schlüsseldateiname** `key.snk`ein.</span><span class="sxs-lookup"><span data-stu-id="a1b24-148">In the **Key file name** box, type `key.snk`.</span></span> <span data-ttu-id="a1b24-149">Deaktivieren Sie das Kontrollkästchen **Schlüsseldatei mit Kennwort schützen**.</span><span class="sxs-lookup"><span data-stu-id="a1b24-149">Clear the **Protect my key file with a password** check box.</span></span> <span data-ttu-id="a1b24-150">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a1b24-150">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="a1b24-151">Öffnen Sie die Datei „ISampleInterface.cs“.</span><span class="sxs-lookup"><span data-stu-id="a1b24-151">Open the ISampleInterface.cs file.</span></span> <span data-ttu-id="a1b24-152">Fügen Sie den folgenden Code zur Klasse „ISampleInterface“ hinzu, um die ISampleInterface-Schnittstelle zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a1b24-152">Add the following code to the ISampleInterface class file to create the ISampleInterface interface.</span></span>  
  
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
  
7.  <span data-ttu-id="a1b24-153">Klicken Sie im Menü **Extras** auf den Befehl **GUID erstellen**.</span><span class="sxs-lookup"><span data-stu-id="a1b24-153">On the **Tools** menu, click **Create Guid**.</span></span> <span data-ttu-id="a1b24-154">Klicken Sie im Dialogfeld **GUID erstellen** auf **Registrierungsformat** und anschließend auf **Kopieren**.</span><span class="sxs-lookup"><span data-stu-id="a1b24-154">In the **Create GUID** dialog box, click **Registry Format** and then click **Copy**.</span></span> <span data-ttu-id="a1b24-155">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="a1b24-155">Click **Exit**.</span></span>  
  
8.  <span data-ttu-id="a1b24-156">Löschen Sie die Beispiel-GUID im Attribut `Guid`, und fügen Sie die GUID ein, die Sie aus dem Dialogfeld **GUID erstellen** kopiert haben.</span><span class="sxs-lookup"><span data-stu-id="a1b24-156">In the `Guid` attribute, delete the sample GUID and paste in the GUID that you copied from the **Create GUID** dialog box.</span></span> <span data-ttu-id="a1b24-157">Entfernen Sie die geschweiften Klammern ({}) aus der kopierten GUID.</span><span class="sxs-lookup"><span data-stu-id="a1b24-157">Remove the braces ({}) from the copied GUID.</span></span>  
  
9. <span data-ttu-id="a1b24-158">Erweitern Sie im **Projektmappen-Explorer** den Ordner **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="a1b24-158">In **Solution Explorer**, expand the **Properties** folder.</span></span> <span data-ttu-id="a1b24-159">Doppelklicken Sie auf die Datei „AssemblyInfo.cs“.</span><span class="sxs-lookup"><span data-stu-id="a1b24-159">Double-click the AssemblyInfo.cs file.</span></span> <span data-ttu-id="a1b24-160">Fügen Sie folgendes Attribut zur Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="a1b24-160">Add the following attribute to the file.</span></span>  
  
    ```csharp  
    [assembly: ImportedFromTypeLib("")]  
    ```  
  
     <span data-ttu-id="a1b24-161">Speichern Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="a1b24-161">Save the file.</span></span>  
  
10. <span data-ttu-id="a1b24-162">Speichern Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="a1b24-162">Save the project.</span></span>  
  
11. <span data-ttu-id="a1b24-163">Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceInterface“, und klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="a1b24-163">Right-click the TypeEquivalenceInterface project and click **Build**.</span></span> <span data-ttu-id="a1b24-164">Die DLL-Datei der Klassenbibliothek wird kompiliert und im angegebenen Buildausgabepfad gespeichert (z.B. C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="a1b24-164">The class library .dll file is compiled and saved to the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="creating-a-runtime-class"></a><span data-ttu-id="a1b24-165">Erstellen einer Runtime-Klasse</span><span class="sxs-lookup"><span data-stu-id="a1b24-165">Creating a Runtime Class</span></span>  
  
#### <a name="to-create-the-type-equivalence-runtime-project"></a><span data-ttu-id="a1b24-166">So erstellen Sie das Runtime-Projekt mit Typäquivalenz</span><span class="sxs-lookup"><span data-stu-id="a1b24-166">To create the type equivalence runtime project</span></span>  
  
1.  <span data-ttu-id="a1b24-167">Zeigen Sie in Visual Studio im Menü **Datei** auf **Neu**, und klicken Sie auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="a1b24-167">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="a1b24-168">Überprüfen Sie, ob im Dialogfeld **Neues Projekt** im Bereich **Projekttypen** der Eintrag **Windows** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="a1b24-168">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="a1b24-169">Wählen Sie im Bereich **Vorlagen** die Option **Klassenbibliothek** aus.</span><span class="sxs-lookup"><span data-stu-id="a1b24-169">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="a1b24-170">Geben Sie im Feld **Name** die Bezeichnung `TypeEquivalenceRuntime` ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a1b24-170">In the **Name** box, type `TypeEquivalenceRuntime`, and then click **OK**.</span></span> <span data-ttu-id="a1b24-171">Das neue Projekt wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="a1b24-171">The new project is created.</span></span>  
  
3.  <span data-ttu-id="a1b24-172">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Datei „Class1.cs“, und klicken Sie auf **Umbenennen**.</span><span class="sxs-lookup"><span data-stu-id="a1b24-172">In **Solution Explorer**, right-click the Class1.cs file and click **Rename**.</span></span> <span data-ttu-id="a1b24-173">Benennen Sie die Datei in `SampleClass.cs` um, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="a1b24-173">Rename the file to `SampleClass.cs` and press ENTER.</span></span> <span data-ttu-id="a1b24-174">Durch Umbenennen der Datei wird die Klasse ebenfalls in `SampleClass` umbenannt.</span><span class="sxs-lookup"><span data-stu-id="a1b24-174">Renaming the file also renames the class to `SampleClass`.</span></span> <span data-ttu-id="a1b24-175">Diese Klasse implementiert die `ISampleInterface`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="a1b24-175">This class will implement the `ISampleInterface` interface.</span></span>  
  
4.  <span data-ttu-id="a1b24-176">Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceRuntime“, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="a1b24-176">Right-click the TypeEquivalenceRuntime project and click **Properties**.</span></span> <span data-ttu-id="a1b24-177">Klicken Sie auf die Registerkarte **Erstellen**. Legen Sie den Ausgabepfad auf denselben Speicherort fest, den Sie im Projekt „TypeEquivalenceInterface“ verwendet haben, z.B. auf `C:\TypeEquivalenceSample`.</span><span class="sxs-lookup"><span data-stu-id="a1b24-177">Click the **Build** tab. Set the output path to the same location you used in the TypeEquivalenceInterface project, for example, `C:\TypeEquivalenceSample`.</span></span>  
  
5.  <span data-ttu-id="a1b24-178">Klicken Sie auf die Schaltfläche **Signierung**, während Sie noch die Projekteigenschaften bearbeiten. Wählen Sie die Option **Assembly signieren** aus.</span><span class="sxs-lookup"><span data-stu-id="a1b24-178">While still editing the project properties, click the **Signing** tab. Select the **Sign the assembly** option.</span></span> <span data-ttu-id="a1b24-179">Klicken Sie in der Liste **Schlüsseldatei mit starkem Namen auswählen** auf **<Neu...>**.</span><span class="sxs-lookup"><span data-stu-id="a1b24-179">In the **Choose a strong name key file** list, click **<New...>**.</span></span> <span data-ttu-id="a1b24-180">Geben Sie im Feld **Schlüsseldateiname** `key.snk`ein.</span><span class="sxs-lookup"><span data-stu-id="a1b24-180">In the **Key file name** box, type `key.snk`.</span></span> <span data-ttu-id="a1b24-181">Deaktivieren Sie das Kontrollkästchen **Schlüsseldatei mit Kennwort schützen**.</span><span class="sxs-lookup"><span data-stu-id="a1b24-181">Clear the **Protect my key file with a password** check box.</span></span> <span data-ttu-id="a1b24-182">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a1b24-182">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="a1b24-183">Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceRuntime“, und klicken Sie auf **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a1b24-183">Right-click the TypeEquivalenceRuntime project and click **Add Reference**.</span></span> <span data-ttu-id="a1b24-184">Klicken Sie auf die Registerkarte **Durchsuchen**, und navigieren Sie zum Ausgabeordner für den Pfad.</span><span class="sxs-lookup"><span data-stu-id="a1b24-184">Click the **Browse** tab and browse to the output path folder.</span></span> <span data-ttu-id="a1b24-185">Wählen Sie die Datei „TypeEquivalenceInterface.dll“ aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a1b24-185">Select the TypeEquivalenceInterface.dll file and click **OK**.</span></span>  
  
7.  <span data-ttu-id="a1b24-186">Erweitern Sie im **Projektmappen-Explorer** den Ordner **Verweise**.</span><span class="sxs-lookup"><span data-stu-id="a1b24-186">In **Solution Explorer**, expand the **References** folder.</span></span> <span data-ttu-id="a1b24-187">Wählen Sie den Verweis „TypeEquivalenceInterface“ aus.</span><span class="sxs-lookup"><span data-stu-id="a1b24-187">Select the TypeEquivalenceInterface reference.</span></span> <span data-ttu-id="a1b24-188">Legen Sie im Eigenschaftenfenster für den Verweis „TypeEquivalenceInterface“ die Eigenschaft **Spezifische Version** auf **False** fest.</span><span class="sxs-lookup"><span data-stu-id="a1b24-188">In the Properties window for the TypeEquivalenceInterface reference, set the **Specific Version** property to **False**.</span></span>  
  
8.  <span data-ttu-id="a1b24-189">Fügen Sie den folgenden Code zur Klassendatei „SampleClass“ hinzu, um die Klasse SampleClass zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a1b24-189">Add the following code to the SampleClass class file to create the SampleClass class.</span></span>  
  
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
  
9. <span data-ttu-id="a1b24-190">Speichern Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="a1b24-190">Save the project.</span></span>  
  
10. <span data-ttu-id="a1b24-191">Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceRuntime“, und klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="a1b24-191">Right-click the TypeEquivalenceRuntime project and click **Build**.</span></span> <span data-ttu-id="a1b24-192">Die DLL-Datei der Klassenbibliothek wird kompiliert und im angegebenen Buildausgabepfad gespeichert (z.B. C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="a1b24-192">The class library .dll file is compiled and saved to the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="creating-a-client-project"></a><span data-ttu-id="a1b24-193">Erstellen eines Clientprojekts</span><span class="sxs-lookup"><span data-stu-id="a1b24-193">Creating a Client Project</span></span>  
  
#### <a name="to-create-the-type-equivalence-client-project"></a><span data-ttu-id="a1b24-194">So erstellen Sie das Clientprojekt mit Typäquivalenz</span><span class="sxs-lookup"><span data-stu-id="a1b24-194">To create the type equivalence client project</span></span>  
  
1.  <span data-ttu-id="a1b24-195">Zeigen Sie in Visual Studio im Menü **Datei** auf **Neu**, und klicken Sie auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="a1b24-195">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="a1b24-196">Überprüfen Sie, ob im Dialogfeld **Neues Projekt** im Bereich **Projekttypen** der Eintrag **Windows** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="a1b24-196">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="a1b24-197">Wählen Sie im Bereich **Vorlagen** die Option **Konsolenanwendung** aus.</span><span class="sxs-lookup"><span data-stu-id="a1b24-197">Select **Console Application** in the **Templates** pane.</span></span> <span data-ttu-id="a1b24-198">Geben Sie im Feld **Name** die Bezeichnung `TypeEquivalenceClient` ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a1b24-198">In the **Name** box, type `TypeEquivalenceClient`, and then click **OK**.</span></span> <span data-ttu-id="a1b24-199">Das neue Projekt wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="a1b24-199">The new project is created.</span></span>  
  
3.  <span data-ttu-id="a1b24-200">Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceClient“, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="a1b24-200">Right-click the TypeEquivalenceClient project and click **Properties**.</span></span> <span data-ttu-id="a1b24-201">Klicken Sie auf die Registerkarte **Erstellen**. Legen Sie den Ausgabepfad auf denselben Speicherort fest, den Sie im Projekt „TypeEquivalenceInterface“ verwendet haben, z.B. auf `C:\TypeEquivalenceSample`.</span><span class="sxs-lookup"><span data-stu-id="a1b24-201">Click the **Build** tab. Set the output path to the same location you used in the TypeEquivalenceInterface project, for example, `C:\TypeEquivalenceSample`.</span></span>  
  
4.  <span data-ttu-id="a1b24-202">Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceClient“, und klicken Sie auf **Verweis Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a1b24-202">Right-click the TypeEquivalenceClient project and click **Add Reference**.</span></span> <span data-ttu-id="a1b24-203">Klicken Sie auf die Registerkarte **Durchsuchen**, und navigieren Sie zum Ausgabeordner für den Pfad.</span><span class="sxs-lookup"><span data-stu-id="a1b24-203">Click the **Browse** tab and browse to the output path folder.</span></span> <span data-ttu-id="a1b24-204">Wählen Sie die Datei „TypeEquivalenceInterface.dll“ aus (nicht „TypeEquivalenceRuntime.dll“), und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a1b24-204">Select the TypeEquivalenceInterface.dll file (not the TypeEquivalenceRuntime.dll) and click **OK**.</span></span>  
  
5.  <span data-ttu-id="a1b24-205">Erweitern Sie im **Projektmappen-Explorer** den Ordner **Verweise**.</span><span class="sxs-lookup"><span data-stu-id="a1b24-205">In **Solution Explorer**, expand the **References** folder.</span></span> <span data-ttu-id="a1b24-206">Wählen Sie den Verweis „TypeEquivalenceInterface“ aus.</span><span class="sxs-lookup"><span data-stu-id="a1b24-206">Select the TypeEquivalenceInterface reference.</span></span> <span data-ttu-id="a1b24-207">Legen Sie im Eigenschaftenfenster für den Verweis „TypeEquivalenceInterface“ die Eigenschaft **Einbetten von Interop-Typen** auf **True** fest.</span><span class="sxs-lookup"><span data-stu-id="a1b24-207">In the Properties window for the TypeEquivalenceInterface reference, set the **Embed Interop Types** property to **True**.</span></span>  
  
6.  <span data-ttu-id="a1b24-208">Fügen Sie folgenden Code zur Datei „Program.cs“ hinzu, um das Clientprogramm zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a1b24-208">Add the following code to the Program.cs file to create the client program.</span></span>  
  
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
  
7.  <span data-ttu-id="a1b24-209">Drücken Sie STRG+F5, um das Programm zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a1b24-209">Press CTRL+F5 to build and run the program.</span></span>  
  
## <a name="modifying-the-interface"></a><span data-ttu-id="a1b24-210">Ändern der Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a1b24-210">Modifying the Interface</span></span>  
  
#### <a name="to-modify-the-interface"></a><span data-ttu-id="a1b24-211">So ändern Sie die Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a1b24-211">To modify the interface</span></span>  
  
1.  <span data-ttu-id="a1b24-212">Zeigen Sie in Visual Studio im Menü **Datei** auf **Öffnen**, und klicken Sie auf **Projekt/Projektmappe**.</span><span class="sxs-lookup"><span data-stu-id="a1b24-212">In Visual Studio, on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
2.  <span data-ttu-id="a1b24-213">Klicken Sie im Dialogfeld **Projekt öffnen** mit der rechten Maustaste auf das Projekt „TypeEquivalenceInterface“, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="a1b24-213">In the **Open Project** dialog box, right-click the TypeEquivalenceInterface project, and then click **Properties**.</span></span> <span data-ttu-id="a1b24-214">Klicken Sie auf die Registerkarte **Anwendung** . Klicken Sie auf die Schaltfläche **Assemblyinformationen**.</span><span class="sxs-lookup"><span data-stu-id="a1b24-214">Click the **Application** tab. Click the **Assembly Information** button.</span></span> <span data-ttu-id="a1b24-215">Ändern Sie die Werte der **Assemblyversion** und der **Dateiversion** in `2.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="a1b24-215">Change the **Assembly Version** and **File Version** values to `2.0.0.0`.</span></span>  
  
3.  <span data-ttu-id="a1b24-216">Öffnen Sie die Datei „SampleInterface.cs“.</span><span class="sxs-lookup"><span data-stu-id="a1b24-216">Open the SampleInterface.cs file.</span></span> <span data-ttu-id="a1b24-217">Fügen Sie der ISampleInterface-Schnittstelle die folgende Codezeile hinzu.</span><span class="sxs-lookup"><span data-stu-id="a1b24-217">Add the following line of code to the ISampleInterface interface.</span></span>  
  
    ```csharp  
    DateTime GetDate();  
    ```  
  
     <span data-ttu-id="a1b24-218">Speichern Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="a1b24-218">Save the file.</span></span>  
  
4.  <span data-ttu-id="a1b24-219">Speichern Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="a1b24-219">Save the project.</span></span>  
  
5.  <span data-ttu-id="a1b24-220">Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceInterface“, und klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="a1b24-220">Right-click the TypeEquivalenceInterface project and click **Build**.</span></span> <span data-ttu-id="a1b24-221">Eine neue Version der DLL-Datei der Klassenbibliothek wird kompiliert und im angegebenen Buildausgabepfad gespeichert (z.B. C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="a1b24-221">A new version of the class library .dll file is compiled and saved in the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="modifying-the-runtime-class"></a><span data-ttu-id="a1b24-222">Ändern der Runtime-Klasse</span><span class="sxs-lookup"><span data-stu-id="a1b24-222">Modifying the Runtime Class</span></span>  
  
#### <a name="to-modify-the-runtime-class"></a><span data-ttu-id="a1b24-223">So ändern Sie die Runtime-Klasse</span><span class="sxs-lookup"><span data-stu-id="a1b24-223">To modify the runtime class</span></span>  
  
1.  <span data-ttu-id="a1b24-224">Zeigen Sie in Visual Studio im Menü **Datei** auf **Öffnen**, und klicken Sie auf **Projekt/Projektmappe**.</span><span class="sxs-lookup"><span data-stu-id="a1b24-224">In Visual Studio, on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
2.  <span data-ttu-id="a1b24-225">Klicken Sie im Dialogfeld **Projekt öffnen** mit der rechten Maustaste auf das Projekt „TypeEquivalenceRuntime“, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="a1b24-225">In the **Open Project** dialog box, right-click the TypeEquivalenceRuntime project and click **Properties**.</span></span> <span data-ttu-id="a1b24-226">Klicken Sie auf die Registerkarte **Anwendung** . Klicken Sie auf die Schaltfläche **Assemblyinformationen**.</span><span class="sxs-lookup"><span data-stu-id="a1b24-226">Click the **Application** tab. Click the **Assembly Information** button.</span></span> <span data-ttu-id="a1b24-227">Ändern Sie die Werte der **Assemblyversion** und der **Dateiversion** in `2.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="a1b24-227">Change the **Assembly Version** and **File Version** values to `2.0.0.0`.</span></span>  
  
3.  <span data-ttu-id="a1b24-228">Öffnen Sie die Datei „SampleClass.cs“.</span><span class="sxs-lookup"><span data-stu-id="a1b24-228">Open the SampleClass.cs file.</span></span> <span data-ttu-id="a1b24-229">Fügen Sie folgenden Codezeilen zur Klasse „SampleClass“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="a1b24-229">Add the following lines of code to the SampleClass class.</span></span>  
  
    ```csharp  
    public DateTime GetDate()  
    {  
        return DateTime.Now;  
    }  
    ```  
  
     <span data-ttu-id="a1b24-230">Speichern Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="a1b24-230">Save the file.</span></span>  
  
4.  <span data-ttu-id="a1b24-231">Speichern Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="a1b24-231">Save the project.</span></span>  
  
5.  <span data-ttu-id="a1b24-232">Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceRuntime“, und klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="a1b24-232">Right-click the TypeEquivalenceRuntime project and click **Build**.</span></span> <span data-ttu-id="a1b24-233">Eine aktualisierte Version der DLL-Datei der Klassenbibliothek wird kompiliert und im vorher angegebenen Buildausgabepfad gespeichert (z.B. C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="a1b24-233">An updated version of the class library .dll file is compiled and saved in the previously specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
6.  <span data-ttu-id="a1b24-234">Öffnen Sie im Datei-Explorer den Ordner mit dem Ausgabepfad (z.B. C:\TypeEquivalenceSample).</span><span class="sxs-lookup"><span data-stu-id="a1b24-234">In File Explorer, open the output path folder (for example, C:\TypeEquivalenceSample).</span></span> <span data-ttu-id="a1b24-235">Doppelklicken Sie auf die Datei „TypeEquivalenceClient.exe“, um das Programm auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a1b24-235">Double-click the TypeEquivalenceClient.exe to run the program.</span></span> <span data-ttu-id="a1b24-236">Das Programm reflektiert die neue Version der TypeEquivalenceRuntime-Assembly, ohne dass sie erneut kompiliert werden muss.</span><span class="sxs-lookup"><span data-stu-id="a1b24-236">The program will reflect the new version of the TypeEquivalenceRuntime assembly without having been recompiled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1b24-237">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1b24-237">See Also</span></span>

- [<span data-ttu-id="a1b24-238">-link (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="a1b24-238">/link (C# Compiler Options)</span></span>](../../../../csharp/language-reference/compiler-options/link-compiler-option.md)  
- [<span data-ttu-id="a1b24-239">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a1b24-239">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="a1b24-240">Programmieren mit Assemblys</span><span class="sxs-lookup"><span data-stu-id="a1b24-240">Programming with Assemblies</span></span>](../../../../framework/app-domains/programming-with-assemblies.md)  
- [<span data-ttu-id="a1b24-241">Assemblies and the Global Assembly Cache (C#) (Assemblys und der globale Assemblycache (C#))</span><span class="sxs-lookup"><span data-stu-id="a1b24-241">Assemblies and the Global Assembly Cache (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)
