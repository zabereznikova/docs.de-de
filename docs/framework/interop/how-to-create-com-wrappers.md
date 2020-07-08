---
title: 'Vorgehensweise: Erstellen von COM-Wrappern'
description: Erstellen Sie COM-Wrapper (Component Object Model) mit Visual Studio- oder .NET-Tools („Tlbimp.exe“ und „Regasm.exe“). Beide Methoden generieren zwei Typen von COM-Wrappern.
ms.date: 03/30/2017
helpviewer_keywords:
- COM,wrappers creating
- COM,wrappers Visual Studio
ms.assetid: bdf89bea-1623-45ee-a57b-cf7c90395efa
ms.openlocfilehash: 286526c710287e6efa3e49a7f7c55e3687076e29
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617391"
---
# <a name="how-to-create-com-wrappers"></a><span data-ttu-id="5646b-104">Vorgehensweise: Erstellen von COM-Wrappern</span><span class="sxs-lookup"><span data-stu-id="5646b-104">How to: Create COM Wrappers</span></span>

<span data-ttu-id="5646b-105">Sie können mit Visual Studio 2005-Features oder den .NET Framework-Tools „Tlbimp.exe“ und „Regasm.exe“ COM-Wrapper (Component Object Model) erstellen.</span><span class="sxs-lookup"><span data-stu-id="5646b-105">You can create Component Object Model (COM) wrappers by using Visual Studio 2005 features or the .NET Framework tools Tlbimp.exe and Regasm.exe.</span></span> <span data-ttu-id="5646b-106">Beide Methoden generieren zwei Typen von COM-Wrappern:</span><span class="sxs-lookup"><span data-stu-id="5646b-106">Both methods generate two types of COM wrappers:</span></span>

- <span data-ttu-id="5646b-107">Ein [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) aus einer Typbibliothek führt ein COM-Objekt in verwaltetem Code aus.</span><span class="sxs-lookup"><span data-stu-id="5646b-107">A [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) from a type library to run a COM object in managed code.</span></span>

- <span data-ttu-id="5646b-108">Ein [COM Callable Wrapper](../../standard/native-interop/com-callable-wrapper.md) mit den erforderlichen Registrierungseinstellungen führt ein verwaltetes Objekt in einer nativen Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="5646b-108">A [COM Callable Wrapper](../../standard/native-interop/com-callable-wrapper.md) with the required registry settings to run a managed object in a native application.</span></span>

<span data-ttu-id="5646b-109">In Visual Studio 2005 können Sie den COM-Wrapper als Verweis zu Ihrem Projekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5646b-109">In Visual Studio 2005, you can add the COM wrapper as a reference to your project.</span></span>

## <a name="wrap-com-objects-in-a-managed-application"></a><span data-ttu-id="5646b-110">Umschließen von COM-Objekten in einer verwalteten Anwendung</span><span class="sxs-lookup"><span data-stu-id="5646b-110">Wrap COM Objects in a Managed Application</span></span>

### <a name="to-create-a-runtime-callable-wrapper-using-visual-studio"></a><span data-ttu-id="5646b-111">Erstellen eines durch die Laufzeit aufrufbaren Wrappers mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5646b-111">To create a runtime callable wrapper using Visual Studio</span></span>

1. <span data-ttu-id="5646b-112">Öffnen Sie das Projekt für Ihre verwaltete Anwendung.</span><span class="sxs-lookup"><span data-stu-id="5646b-112">Open the project for your managed application.</span></span>

2. <span data-ttu-id="5646b-113">Klicken Sie im Menü **Projekt** auf **Alle Dateien anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="5646b-113">On the **Project** menu, click **Show All Files**.</span></span>

3. <span data-ttu-id="5646b-114">Klicken Sie im Menü **Projekt** auf **Verweis hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="5646b-114">On the **Project** menu, click **Add Reference**.</span></span>

4. <span data-ttu-id="5646b-115">Klicken Sie im Dialogfeld „Verweis hinzufügen“ auf die Registerkarte **COM**, wählen Sie die Komponente aus, die Sie verwenden möchten, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5646b-115">In the Add Reference dialog box, click the **COM** tab, select the component you want to use, and click **OK**.</span></span>

     <span data-ttu-id="5646b-116">Beachten Sie, dass die COM-Komponente im **Projektmappen-Explorer** dem Projektordner „Verweise“ hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="5646b-116">In **Solution Explorer**, note that the COM component is added to the References folder in your project.</span></span>

<span data-ttu-id="5646b-117">Sie können jetzt Code schreiben, um auf das COM-Objekt zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="5646b-117">You can now write code to access the COM object.</span></span> <span data-ttu-id="5646b-118">Sie können mit der Objektdeklaration beginnen, zum Beispiel mit einer `Imports`-Anweisung für Visual Basic oder einer `Using`-Anweisung für C#.</span><span class="sxs-lookup"><span data-stu-id="5646b-118">You can begin by declaring the object, such as with an `Imports` statement for Visual Basic or a `Using` statement for C#.</span></span>

> [!NOTE]
> <span data-ttu-id="5646b-119">Wenn Sie Microsoft Office-Komponenten programmieren möchten, installieren Sie zunächst das [Redistributable für primäre Interop-Assemblys von Microsoft Office](https://www.microsoft.com/Download/details.aspx?id=3508).</span><span class="sxs-lookup"><span data-stu-id="5646b-119">If you want to program Microsoft Office components, first install the [Microsoft Office Primary Interop Assemblies Redistributable](https://www.microsoft.com/Download/details.aspx?id=3508).</span></span>
  
### <a name="to-create-a-runtime-callable-wrapper-using-net-framework-tools"></a><span data-ttu-id="5646b-120">Erstellen eines Runtime Callable Wrappers mit .NET Framework-Tools</span><span class="sxs-lookup"><span data-stu-id="5646b-120">To create a runtime callable wrapper using .NET Framework tools</span></span>  
  
- <span data-ttu-id="5646b-121">Führen Sie das [Tlbimp.exe (Type Library Importer-Tool)](../tools/tlbimp-exe-type-library-importer.md) aus.</span><span class="sxs-lookup"><span data-stu-id="5646b-121">Run the [Tlbimp.exe (Type Library Importer)](../tools/tlbimp-exe-type-library-importer.md) tool.</span></span>  
  
 <span data-ttu-id="5646b-122">Dieses Tool erstellt eine Assembly, die Laufzeitmetadaten für die Typen enthält, die in der ursprünglichen Typbibliothek definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="5646b-122">This tool creates an assembly that contains run-time metadata for the types defined in the original type library.</span></span>  
  
## <a name="wrap-managed-objects-in-a-native-application"></a><span data-ttu-id="5646b-123">Umschließen von verwalteten Objekten in einer nativen Anwendung</span><span class="sxs-lookup"><span data-stu-id="5646b-123">Wrap Managed Objects in a Native Application</span></span>  
  
### <a name="to-create-a-com-callable-wrapper-using-visual-studio"></a><span data-ttu-id="5646b-124">Erstellen eines COM Callable Wrappers mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5646b-124">To create a COM callable wrapper using Visual Studio</span></span>  
  
1. <span data-ttu-id="5646b-125">Erstellen Sie ein Klassenbibliotheksprojekt für die verwaltete Klasse, die Sie in nativem Code ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="5646b-125">Create a Class Library project for the managed class that you want to run in native code.</span></span> <span data-ttu-id="5646b-126">Die Klasse muss einen parameterlosen Konstruktor haben.</span><span class="sxs-lookup"><span data-stu-id="5646b-126">The class must have a parameterless constructor.</span></span>  
  
     <span data-ttu-id="5646b-127">Überprüfen Sie, ob Sie eine vollständige vierteilige Versionsnummer für die Assembly in der AssemblyInfo-Datei besitzen.</span><span class="sxs-lookup"><span data-stu-id="5646b-127">Verify that you have a complete four-part version number for your assembly in the AssemblyInfo file.</span></span> <span data-ttu-id="5646b-128">Diese Zahl ist für die Versionszuweisung in der Windows-Registrierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5646b-128">This number is required for maintaining versioning in the Windows registry.</span></span> <span data-ttu-id="5646b-129">Weitere Informationen über die Versionsummern finden Sie unter [Assemblyversionen](../../standard/assembly/versioning.md).</span><span class="sxs-lookup"><span data-stu-id="5646b-129">For more information about version numbers, see [Assembly Versioning](../../standard/assembly/versioning.md).</span></span>  
  
2. <span data-ttu-id="5646b-130">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="5646b-130">On the **Project** menu, click **Properties**.</span></span>  
  
3. <span data-ttu-id="5646b-131">Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="5646b-131">Click the **Compile** tab.</span></span>  
  
4. <span data-ttu-id="5646b-132">Aktivieren Sie das Kontrollkästchen **Für COM-Interop registrieren**.</span><span class="sxs-lookup"><span data-stu-id="5646b-132">Select the **Register for COM interop** check box.</span></span>  
  
 <span data-ttu-id="5646b-133">Wenn Sie das Projekt erstellen, wird die Assembly für COM-Interop automatisch registriert.</span><span class="sxs-lookup"><span data-stu-id="5646b-133">When you build the project, the assembly is automatically registered for COM interop.</span></span> <span data-ttu-id="5646b-134">Wenn Sie in Visual Studio 2005 eine native Anwendung erstellen, können Sie die Assembly verwenden, indem Sie im Menü **Projekt** auf **Verweis hinzufügen** klicken.</span><span class="sxs-lookup"><span data-stu-id="5646b-134">If you are building a native application in Visual Studio 2005, you can use the assembly by clicking **Add Reference** on the **Project** menu.</span></span>  
  
### <a name="to-create-a-com-callable-wrapper-using-net-framework-tools"></a><span data-ttu-id="5646b-135">Erstellen eines COM Callable Wrappers mit .NET Framework-Tools</span><span class="sxs-lookup"><span data-stu-id="5646b-135">To create a COM callable wrapper using .NET Framework tools</span></span>  
  
<span data-ttu-id="5646b-136">Führen Sie das Tool [Regasm.exe (Assembly Registration-Tool)](../tools/regasm-exe-assembly-registration-tool.md) aus.</span><span class="sxs-lookup"><span data-stu-id="5646b-136">Run the [Regasm.exe (Assembly Registration Tool)](../tools/regasm-exe-assembly-registration-tool.md) tool.</span></span>  
  
<span data-ttu-id="5646b-137">Dieses Tool liest die Metadaten in einer Assembly und fügt der Registrierung die notwendigen Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="5646b-137">This tool reads the assembly metadata and adds the necessary entries to the registry.</span></span> <span data-ttu-id="5646b-138">Folglich können COM-Clients .NET Framework-Klassen transparent erstellen.</span><span class="sxs-lookup"><span data-stu-id="5646b-138">As a result, COM clients can create .NET Framework classes transparently.</span></span> <span data-ttu-id="5646b-139">Sie können die Assembly verwenden, als handle es sich um eine native COM-Klasse.</span><span class="sxs-lookup"><span data-stu-id="5646b-139">You can use the assembly as if it were a native COM class.</span></span>  
  
<span data-ttu-id="5646b-140">Sie können Regasm.exe für eine Assembly in jedem beliebigen Verzeichnis ausführen und anschließend das [Gacutil.exe (Global Assembly Cache Tool)](../tools/gacutil-exe-gac-tool.md) ausführen, um sie in den globalen Assemblycache zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="5646b-140">You can run Regasm.exe on an assembly located in any directory, and then run the [Gacutil.exe (Global Assembly Cache Tool)](../tools/gacutil-exe-gac-tool.md) to move it to the global assembly cache.</span></span> <span data-ttu-id="5646b-141">Beim Verschieben der Assembly werden die Registrierungseinträge für den Speicherort nicht ungültig, da der globale Assemblycache immer überprüft wird, wenn die Assembly nicht an einem anderen Speicherort gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="5646b-141">Moving the assembly does not invalidate location registry entries, because the global assembly cache is always examined if the assembly is not found elsewhere.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5646b-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5646b-142">See also</span></span>

- [<span data-ttu-id="5646b-143">Runtime Callable Wrapper (RCW)</span><span class="sxs-lookup"><span data-stu-id="5646b-143">Runtime Callable Wrapper</span></span>](../../standard/native-interop/runtime-callable-wrapper.md)
- [<span data-ttu-id="5646b-144">COM Callable Wrapper</span><span class="sxs-lookup"><span data-stu-id="5646b-144">COM Callable Wrapper</span></span>](../../standard/native-interop/com-callable-wrapper.md)
