---
title: 'Gewusst wie: Installieren einer Assembly in den globalen Assemblycache'
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- global assembly cache, installing assemblies
- Global Assembly Cache tool
ms.assetid: a7e6f091-d02c-49ba-b736-7295cb0eb743
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed6519cb6bb7006f62ef83cd6baf8f2e32a44d19
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-install-an-assembly-into-the-global-assembly-cache"></a><span data-ttu-id="5fa70-102">Gewusst wie: Installieren einer Assembly in den globalen Assemblycache</span><span class="sxs-lookup"><span data-stu-id="5fa70-102">How to: Install an Assembly into the Global Assembly Cache</span></span>
<span data-ttu-id="5fa70-103">Es gibt zwei Möglichkeiten, eine Assembly mit starkem Namen im globalen Assemblycache (GAC) zu installieren:</span><span class="sxs-lookup"><span data-stu-id="5fa70-103">There are two ways to install a strong-named assembly into the global assembly cache (GAC):</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5fa70-104">Nur Assemblys mit starkem Namen können im GAC installiert werden.</span><span class="sxs-lookup"><span data-stu-id="5fa70-104">Only strong-named assemblies can be installed into the GAC.</span></span> <span data-ttu-id="5fa70-105">Informationen zum Erstellen einer Assembly mit starkem Namen finden Sie unter [How to: Sign an Assembly with a Strong Name (Vorgehensweise: Signieren einer Assembly mit einem starken Namen)](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="5fa70-105">For information about how to create a strong-named assembly, see [How to: Sign an Assembly with a Strong Name](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>  
  
-   <span data-ttu-id="5fa70-106">Verwenden des [Windows Installer](http://msdn.microsoft.com/library/windows/desktop/cc185688.aspx)</span><span class="sxs-lookup"><span data-stu-id="5fa70-106">Using [Windows Installer](http://msdn.microsoft.com/library/windows/desktop/cc185688.aspx).</span></span>  
  
     <span data-ttu-id="5fa70-107">Hierzu erstellen Sie in Visual Studio 2012 und Visual Studio 2013 ein InstallShield Limited Edition-Projekt.</span><span class="sxs-lookup"><span data-stu-id="5fa70-107">You do this in Visual Studio 2012 and Visual Studio 2013 by creating an InstallShield Limited Edition Project.</span></span>  
  
     <span data-ttu-id="5fa70-108">Dies ist die empfohlene und auch gebräuchlichste Art, Assemblys zum globalen Assemblycache hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="5fa70-108">This is the recommended and most common way to add assemblies to the global assembly cache.</span></span> <span data-ttu-id="5fa70-109">Der Installer bietet neben einem Verweiszähler für Assemblys im globalen Assemblycache noch weitere Vorteile.</span><span class="sxs-lookup"><span data-stu-id="5fa70-109">The installer provides reference counting of assemblies in the global assembly cache, plus other benefits.</span></span>  
  
-   <span data-ttu-id="5fa70-110">Verwenden des [Global Assembly Cache-Tools (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)</span><span class="sxs-lookup"><span data-stu-id="5fa70-110">Using the [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md).</span></span>  
  
     <span data-ttu-id="5fa70-111">Mit Gacutil.exe können Sie Assemblys mit starkem Namen zum globalen Assemblycache hinzufügen und sich dessen Inhalt anzeigen lassen.</span><span class="sxs-lookup"><span data-stu-id="5fa70-111">You can use Gacutil.exe to add strong-named assemblies to the global assembly cache and to view the contents of the global assembly cache.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5fa70-112">Gacutil.exe ist Entwicklungszwecken vorbehalten und nicht für die Installation von Produktionsassemblys im globalen Assemblycache vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="5fa70-112">Gacutil.exe is only for development purposes and should not be used to install production assemblies into the global assembly cache.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5fa70-113">In früheren Versionen von .NET Framework ermöglichte die Windows Shell-Erweiterung "Shfusion.dll" das Installieren von Assemblys durch Ziehen in Datei-Explorer.</span><span class="sxs-lookup"><span data-stu-id="5fa70-113">In earlier versions of the .NET Framework, the Shfusion.dll Windows shell extension enabled you to install assemblies by dragging them in File Explorer.</span></span> <span data-ttu-id="5fa70-114">Ab [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] ist Shfusion.dll veraltet.</span><span class="sxs-lookup"><span data-stu-id="5fa70-114">Beginning with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Shfusion.dll is obsolete.</span></span>  
  
### <a name="to-use-the-global-assembly-cache-tool-gacutilexe"></a><span data-ttu-id="5fa70-115">So verwenden Sie das Global Assembly Cache-Tool (Gacutil.exe)</span><span class="sxs-lookup"><span data-stu-id="5fa70-115">To use the Global Assembly Cache tool (Gacutil.exe)</span></span>  
  
1.  <span data-ttu-id="5fa70-116">Geben Sie an der Eingabeaufforderung folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="5fa70-116">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="5fa70-117">**gacutil -i** \<*assemblyname*></span><span class="sxs-lookup"><span data-stu-id="5fa70-117">**gacutil -i** \<*assembly name*></span></span>  
  
     <span data-ttu-id="5fa70-118">In diesem Befehl bezeichnet *Assemblyname* den Namen der Assembly, die im globalen Assemblycache installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="5fa70-118">In this command, *assembly name* is the name of the assembly to install in the global assembly cache.</span></span>  
  
 <span data-ttu-id="5fa70-119">Im folgenden Beispiel wird eine Assembly mit dem Dateinamen `hello.dll` im globalen Assemblycache installiert.</span><span class="sxs-lookup"><span data-stu-id="5fa70-119">The following example installs an assembly with the file name `hello.dll` into the global assembly cache.</span></span>  
  
```  
gacutil -i hello.dll  
```  
  
 <span data-ttu-id="5fa70-120">Weitere Informationen finden Sie unter [Global Assembly Cache-Tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md).</span><span class="sxs-lookup"><span data-stu-id="5fa70-120">For more information, see [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md).</span></span>  
  
### <a name="to-use-an-installshield-limited-edition-project"></a><span data-ttu-id="5fa70-121">So verwenden Sie ein InstallShield Limited Edition-Projekt</span><span class="sxs-lookup"><span data-stu-id="5fa70-121">To use an InstallShield Limited Edition Project</span></span>  
  
1.  <span data-ttu-id="5fa70-122">Fügen Sie Ihrer Projektmappe ein Setup- und Bereitstellungspaket hinzu. Öffnen Sie hierfür das Kontextmenü Ihrer Projektmappe, und wählen Sie dann **Hinzufügen**, **Neues Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="5fa70-122">Add a setup and deployment package to your solution by opening the shortcut menu for your solution, and then choosing **Add**, **New Project**.</span></span>  
  
2.  <span data-ttu-id="5fa70-123">Wählen Sie im Dialogfeld **Neues Projekt hinzufügen** im Ordner **Installiert** nacheinander **Andere Projekttypen**, **Setup und Bereitstellung** und dann **InstallShield Limited Edition** aus, und geben Sie Ihrem Projekt einen Namen.</span><span class="sxs-lookup"><span data-stu-id="5fa70-123">In the **Add New Project** dialog box, in the **Installed** folder, choose **Other Project Types**,  **Setup and Deployment**, **InstallShield Limited Edition**, and give your project a name.</span></span> <span data-ttu-id="5fa70-124">Wenn Sie dazu aufgefordert werden, laden Sie InstallShield herunter und installieren und aktivieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="5fa70-124">(If prompted, download, install, and activate InstallShield.)</span></span>  
  
3.  <span data-ttu-id="5fa70-125">Sie können die allgemeine Konfiguration des Setup- und Bereitstellungsprojekts entweder mit dem Projekt-Assistent im **Projektmappen-Explorer** ausführen, oder indem Sie die Teilschritte der nummerierten Schritte im **Projektmappen-Explorer** auswählen. Konfigurieren Sie das Setup genauso, als wenn Sie keine Assemblys in den GAC hinzufügen würden.</span><span class="sxs-lookup"><span data-stu-id="5fa70-125">Perform the general configuration of your setup and deployment project either by using the Project Assistant in **Solution Explorer**, or by choosing the substeps of the numbered steps in the **Solution Explorer**.Configure your setup as you would if you were not adding assemblies to the GAC.</span></span>  
  
4.  <span data-ttu-id="5fa70-126">Beginnen Sie, dem GAC eine Assembly hinzuzufügen, indem Sie **Dateien** (unter dem Schritt **Anwendungsdaten angeben** im **Projektmappen-Explorer**) auswählen.</span><span class="sxs-lookup"><span data-stu-id="5fa70-126">To begin the process of adding an assembly to the GAC, choose **Files**, which is under the **Specify Application Data** step in **Solution Explorer**.</span></span>  
  
5.  <span data-ttu-id="5fa70-127">Öffnen Sie im Bereich **Ordner des Zielcomputers** das Kontextmenü für **Zielcomputer**, und wählen Sie dann **Vordefinierten Ordner anzeigen**, **[GlobalAssemblyCache]** aus.</span><span class="sxs-lookup"><span data-stu-id="5fa70-127">In the **Destination computer's folders** pane, open the shortcut menu for **Destination Computer**, and then choose **Show Predefined Folder**, **[GlobalAssemblyCache]**.</span></span>  
  
6.  <span data-ttu-id="5fa70-128">Führen Sie folgende Schritte für jedes Projekt in der Projektmappe aus, das eine Assembly enthält, die Sie im globalen Assemblycache installieren möchten:</span><span class="sxs-lookup"><span data-stu-id="5fa70-128">For each project in the solution that contains an assembly that you want to install in the global assembly cache:</span></span>  
  
    1.  <span data-ttu-id="5fa70-129">Wählen Sie im Bereich **Ordner des Quellcomputers** das Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="5fa70-129">In the **Source computer's folders** pane, choose the project.</span></span>  
  
    2.  <span data-ttu-id="5fa70-130">Wählen Sie im Bereich **Ordner des Zielcomputers** den Eintrag **[GlobalAssemblyCache]** aus.</span><span class="sxs-lookup"><span data-stu-id="5fa70-130">In the **Destination computer's folders** pane, choose **[GlobalAssemblyCache]**.</span></span>  
  
    3.  <span data-ttu-id="5fa70-131">Wählen Sie im Bereich **Dateien des Quellcomputers** den Eintrag **Primäre Ausgabe von** *<projekt_name>* aus.</span><span class="sxs-lookup"><span data-stu-id="5fa70-131">In the **Source computer's files** pane, choose **Primary output from** *<project_name>*.</span></span>  
  
    4.  <span data-ttu-id="5fa70-132">Ziehen Sie die Datei in Schritt c in den Bereich **Dateien des Zielcomputers** (oder verwenden Sie die Befehle **Kopieren** und **Einfügen** im Kontextmenü der Datei).</span><span class="sxs-lookup"><span data-stu-id="5fa70-132">Drag the file in step c to the **Destination computer's files** pane (or use the **Copy** and **Paste** commands from the file's shortcut menu).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fa70-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5fa70-133">See Also</span></span>  
 [<span data-ttu-id="5fa70-134">Arbeiten mit Assemblys und dem globalen Assemblychache</span><span class="sxs-lookup"><span data-stu-id="5fa70-134">Working with Assemblies and the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 [<span data-ttu-id="5fa70-135">Gewusst wie: Entfernen einer Assembly aus dem globalen Assemblycache</span><span class="sxs-lookup"><span data-stu-id="5fa70-135">How to: Remove an Assembly from the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/how-to-remove-an-assembly-from-the-gac.md)  
 [<span data-ttu-id="5fa70-136">Gacutil.exe (Global Assembly Cache-Tool)</span><span class="sxs-lookup"><span data-stu-id="5fa70-136">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../../../docs/framework/tools/gacutil-exe-gac-tool.md)  
 [<span data-ttu-id="5fa70-137">Vorgehensweise: Signieren einer Assembly mit einem starken Namen</span><span class="sxs-lookup"><span data-stu-id="5fa70-137">How to: Sign an Assembly with a Strong Name</span></span>](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)  
 [<span data-ttu-id="5fa70-138">Windows Installer-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="5fa70-138">Windows Installer Deployment</span></span>](http://msdn.microsoft.com/library/121be21b-b916-43e2-8f10-8b080516d2a0)
