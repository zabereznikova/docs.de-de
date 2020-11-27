---
title: Handbuch für die Bereitstellung von .NET Framework für Administratoren
description: Lesen Sie das Handbuch für die Bereitstellung von .NET für Administratoren. Stellen Sie anhand dieser Informationen die .NET Version 4.5 und ihre Systemabhängigkeiten in einem Netzwerk bereit.
ms.date: 04/10/2018
helpviewer_keywords:
- administrator's guide, deploying .NET Framework
- deployment [.NET Framework], administrator's guide
ms.assetid: bee14036-0436-44e8-89f5-4bc61317977a
ms.openlocfilehash: 12076334d3ede0c8ab9b618ba2018f23c9fc6ae4
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94817093"
---
# <a name="net-framework-deployment-guide-for-administrators"></a><span data-ttu-id="e1dd8-104">Handbuch für die Bereitstellung von .NET Framework für Administratoren</span><span class="sxs-lookup"><span data-stu-id="e1dd8-104">.NET Framework Deployment Guide for Administrators</span></span>

<span data-ttu-id="e1dd8-105">In diesem Artikel wird ausführlich beschrieben, wie Systemadministratoren .NET Framework 4.5 und die zugehörigen Systemabhängigkeiten in einem Netzwerk mit Microsoft Endpoint Configuration Manager bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-105">This step-by-step article describes how a system administrator can deploy .NET Framework 4.5 and its system dependencies across a network by using Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="e1dd8-106">In diesem Artikel wird davon ausgegangen, dass alle Zielclientcomputer die Mindestanforderungen für das .NET Framework erfüllen.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-106">This article assumes that all target client computers meet the minimum requirements for .NET Framework.</span></span> <span data-ttu-id="e1dd8-107">Eine Liste mit den Software- und Hardwareanforderungen für die Installation von .NET Framework 4.5 finden Sie unter [Systemanforderungen für .NET Framework](../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1dd8-107">For a list of the software and hardware requirements for installing .NET Framework 4.5, see [System Requirements](../get-started/system-requirements.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e1dd8-108">Die Software, auf die in diesem Dokument verwiesen wird (einschließlich .NET Framework 4.5, Configuration Manager und Active Directory), unterliegt ohne Einschränkungen den jeweils geltenden Lizenzbedingungen.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-108">The software referenced in this document, including, without limitation, .NET Framework 4.5, Configuration Manager, and Active Directory, are each subject to license terms and conditions.</span></span> <span data-ttu-id="e1dd8-109">In diesen Anweisungen wird vorausgesetzt, dass die Lizenzbestimmungen von den entsprechenden Lizenznehmern der Software gelesen und akzeptiert wurden.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-109">These instructions assume that such license terms and conditions have been reviewed and accepted by the appropriate licensees of the software.</span></span> <span data-ttu-id="e1dd8-110">Diese Anweisungen bedeuten keinen Verzicht auf die Bestimmungen von Lizenzvereinbarungen.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-110">These instructions do not waive any of the terms and conditions of such license agreements.</span></span>
>
> <span data-ttu-id="e1dd8-111">Informationen zur Unterstützung für das .NET Framework finden Sie unter [Offizielle .NET Framework-Supportrichtlinie](https://dotnet.microsoft.com/platform/support/policy/dotnet-framework) auf der Supportwebsite von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-111">For information about support for .NET Framework, see [.NET Framework official support policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-framework) on the Microsoft Support website.</span></span>

<span data-ttu-id="e1dd8-112">Dieses Thema enthält folgende Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="e1dd8-112">This topic contains the following sections:</span></span>

- [<span data-ttu-id="e1dd8-113">Bereitstellungsprozess</span><span class="sxs-lookup"><span data-stu-id="e1dd8-113">The deployment process</span></span>](#the_deployment_process)
- [<span data-ttu-id="e1dd8-114">Bereitstellen des .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e1dd8-114">Deploying .NET Framework</span></span>](#deploying_in_a_test_environment)
- [<span data-ttu-id="e1dd8-115">Erstellen einer Sammlung</span><span class="sxs-lookup"><span data-stu-id="e1dd8-115">Create a collection</span></span>](#creating_a_collection)
- [<span data-ttu-id="e1dd8-116">Erstellen eines Pakets und Programms</span><span class="sxs-lookup"><span data-stu-id="e1dd8-116">Create a package and program</span></span>](#creating_a_package)
- [<span data-ttu-id="e1dd8-117">Auswählen eines Verteilungspunkts</span><span class="sxs-lookup"><span data-stu-id="e1dd8-117">Select a distribution point</span></span>](#select_dist_point)
- [<span data-ttu-id="e1dd8-118">Bereitstellen des Pakets</span><span class="sxs-lookup"><span data-stu-id="e1dd8-118">Deploy the package</span></span>](#deploying_package)
- [<span data-ttu-id="e1dd8-119">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="e1dd8-119">Resources</span></span>](#resources)
- [<span data-ttu-id="e1dd8-120">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="e1dd8-120">Troubleshooting</span></span>](#troubleshooting)

<a name="the_deployment_process"></a>

## <a name="the-deployment-process"></a><span data-ttu-id="e1dd8-121">Bereitstellungsprozess</span><span class="sxs-lookup"><span data-stu-id="e1dd8-121">The deployment process</span></span>

<span data-ttu-id="e1dd8-122">Wenn Sie die unterstützende Infrastruktur eingerichtet haben, stellen Sie das verteilbare .NET Framework-Paket mit Configuration Manager auf Computern im Netzwerk bereit.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-122">When you have the supporting infrastructure in place, you use Configuration Manager to deploy the .NET Framework redistributable package to computers on the network.</span></span> <span data-ttu-id="e1dd8-123">Der Aufbau der Infrastruktur umfasst das Erstellen und Definieren von fünf primären Bereichen: Sammlungen, ein Paket und ein Programm für die Software, Verteilungspunkte und Bereitstellungen.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-123">Building the infrastructure involves creating and defining five primary areas: collections, a package and program for the software, distribution points, and deployments.</span></span>

- <span data-ttu-id="e1dd8-124">Bei **Sammlungen** handelt es sich um Gruppen von Configuration Manager-Ressourcen (z. B. Benutzer, Benutzergruppen oder Computer), für die das .NET Framework bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-124">**Collections** are groups of Configuration Manager resources, such as users, user groups, or computers, to which .NET Framework is deployed.</span></span> <span data-ttu-id="e1dd8-125">Weitere Informationen finden Sie in der Configuration Manager-Dokumentationsbibliothek unter [Einführung in Sammlungen in Configuration Manager](/configmgr/core/clients/manage/collections/introduction-to-collections).</span><span class="sxs-lookup"><span data-stu-id="e1dd8-125">For more information, see [Introduction to collections in Configuration Manager](/configmgr/core/clients/manage/collections/introduction-to-collections) in the Configuration Manager documentation library.</span></span>

- <span data-ttu-id="e1dd8-126">**Pakete und Programme** stellen in der Regel Softwareanwendungen dar, die auf einem Clientcomputer installiert werden, sie können jedoch auch einzelne Dateien, Updates oder sogar einzelne Befehle enthalten.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-126">**Packages and programs** typically represent software applications to be installed on a client computer, but they might also contain individual files, updates, or even individual commands.</span></span> <span data-ttu-id="e1dd8-127">Weitere Informationen finden Sie in der Configuration Manager-Dokumentationsbibliothek unter [Pakete und Programme in Configuration Manager](/configmgr/apps/deploy-use/packages-and-programs).</span><span class="sxs-lookup"><span data-stu-id="e1dd8-127">For more information, see [Packages and programs in Configuration Manager](/configmgr/apps/deploy-use/packages-and-programs) in the Configuration Manager documentation library.</span></span>

- <span data-ttu-id="e1dd8-128">**Verteilungspunkte** sind Configuration Manager-Standortsystemrollen, die zum Ausführen von Software auf Clientcomputern erforderliche Dateien speichern.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-128">**Distribution points** are Configuration Manager site system roles that store files required for software to run on client computers.</span></span> <span data-ttu-id="e1dd8-129">Wenn der Configuration Manager-Client eine Softwarebereitstellung empfängt und verarbeitet, stellt er eine Verbindung mit einem Verteilungspunkt her, um den mit der Software verbundenen Inhalt herunterzuladen und den Installationsvorgang zu starten.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-129">When the Configuration Manager client receives and processes a software deployment, it contacts a distribution point to download the content associated with the software and to start the installation process.</span></span> <span data-ttu-id="e1dd8-130">Weitere Informationen finden Sie in der Configuration Manager-Dokumentationsbibliothek unter [Grundlegende Konzepte für die Inhaltsverwaltung in Configuration Manager](/configmgr/core/plan-design/hierarchy/fundamental-concepts-for-content-management).</span><span class="sxs-lookup"><span data-stu-id="e1dd8-130">For more information, see [Fundamental concepts for content management in Configuration Manager](/configmgr/core/plan-design/hierarchy/fundamental-concepts-for-content-management) in the Configuration Manager documentation library.</span></span>

- <span data-ttu-id="e1dd8-131">**Bereitstellungen** weisen zutreffende Member der angegebenen Zielsammlung an, das Softwarepaket zu installieren.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-131">**Deployments** instruct applicable members of the specified target collection to install the software package.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e1dd8-132">Die Prozeduren in diesem Thema enthalten typische Einstellungen für das Erstellen und Bereitstellen eines Pakets und Programms und umfassen möglicherweise nicht alle möglichen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-132">The procedures in this topic contain typical settings for creating and deploying a package and program, and might not cover all possible settings.</span></span> <span data-ttu-id="e1dd8-133">Weitere Bereitstellungsoptionen im Configuration Manager finden Sie in der [Dokumentationsbibliothek zum Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682041(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="e1dd8-133">For other Configuration Manager deployment options, see the [Configuration Manager Documentation Library](/previous-versions/system-center/system-center-2012-R2/gg682041(v=technet.10)).</span></span>

<a name="deploying_in_a_test_environment"></a>

## <a name="deploying-net-framework"></a><span data-ttu-id="e1dd8-134">Bereitstellen des .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e1dd8-134">Deploying .NET Framework</span></span>

<span data-ttu-id="e1dd8-135">Sie können mit Configuration Manager eine automatische Installation von .NET Framework 4.5 bereitstellen, bei der die Benutzer nicht in den Installationsvorgang eingreifen.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-135">You can use Configuration Manager to deploy a silent installation of .NET Framework 4.5, where the users do not interact with the installation process.</span></span> <span data-ttu-id="e1dd8-136">Führen Sie folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="e1dd8-136">Follow these steps:</span></span>

1. <span data-ttu-id="e1dd8-137">[Erstellen Sie eine Sammlung](#creating_a_collection).</span><span class="sxs-lookup"><span data-stu-id="e1dd8-137">[Create a collection](#creating_a_collection).</span></span>

2. <span data-ttu-id="e1dd8-138">[Erstellen Sie ein Paket und Programm für das verteilbare .NET Framework-Paket](#creating_a_package).</span><span class="sxs-lookup"><span data-stu-id="e1dd8-138">[Create a package and program for the .NET Framework redistributable](#creating_a_package).</span></span>

3. <span data-ttu-id="e1dd8-139">[Wählen Sie einen Verteilungspunkt aus](#select_dist_point).</span><span class="sxs-lookup"><span data-stu-id="e1dd8-139">[Select a distribution point](#select_dist_point).</span></span>

4. <span data-ttu-id="e1dd8-140">[Stellen Sie das Paket bereit](#deploying_package).</span><span class="sxs-lookup"><span data-stu-id="e1dd8-140">[Deploy the package](#deploying_package).</span></span>

<a name="creating_a_collection"></a>

### <a name="create-a-collection"></a><span data-ttu-id="e1dd8-141">Erstellen einer Sammlung</span><span class="sxs-lookup"><span data-stu-id="e1dd8-141">Create a collection</span></span>

<span data-ttu-id="e1dd8-142">In diesem Schritt wählen Sie die Computer aus, auf denen Sie das Paket und Programm bereitstellen, und gruppieren sie in einer Gerätesammlung.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-142">In this step, you select the computers to which you will deploy the package and program, and group them into a device collection.</span></span> <span data-ttu-id="e1dd8-143">Zum Erstellen einer Sammlung im Configuration Manager können Sie Regeln für die direkte Mitgliedschaft verwenden (wobei Sie die Sammlungsmitglieder manuell angeben). Alternativ können Sie Abfrageregeln verwenden (wobei die Sammlungsmitglieder vom Configuration Manager auf der Grundlage von Kriterien bestimmt werden, die Sie angegeben haben).</span><span class="sxs-lookup"><span data-stu-id="e1dd8-143">To create a collection in Configuration Manager, you can use direct membership rules (where you manually specify the collection members) or query rules (where Configuration Manager determines the collection members based on criteria you specify).</span></span> <span data-ttu-id="e1dd8-144">Weitere Informationen zu abfragebezogenen und direkten Mitgliedschaftsregeln finden Sie in der Configuration Manager-Dokumentationsbibliothek unter [Einführung in Sammlungen in Configuration Manager](/configmgr/core/clients/manage/collections/introduction-to-collections).</span><span class="sxs-lookup"><span data-stu-id="e1dd8-144">For more information about membership rules, including queries and direct rules, see [Introduction to collections in Configuration Manager](/configmgr/core/clients/manage/collections/introduction-to-collections) in the Configuration Manager Documentation Library.</span></span>

<span data-ttu-id="e1dd8-145">So erstellen Sie eine Sammlung</span><span class="sxs-lookup"><span data-stu-id="e1dd8-145">To create a collection:</span></span>

1. <span data-ttu-id="e1dd8-146">Wählen Sie in der Configuration Manager-Konsole **Bestand und Kompatibilität** aus.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-146">In the Configuration Manager console, choose **Assets and Compliance**.</span></span>

2. <span data-ttu-id="e1dd8-147">Wählen Sie im Arbeitsbereich **Bestand und Kompatibilität** die Option **Gerätesammlungen** aus.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-147">In the **Assets and Compliance** workspace, choose **Device Collections**.</span></span>

3. <span data-ttu-id="e1dd8-148">Wählen Sie auf der Registerkarte **Startseite** in der Gruppe **Erstellen** die Option **Gerätesammlung erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-148">On the **Home** tab in the **Create** group, choose **Create Device Collection**.</span></span>

4. <span data-ttu-id="e1dd8-149">Geben Sie im **Assistent zum Erstellen von Gerätesammlungen** auf der Seite **Allgemein** einen Namen für die Auflistung ein.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-149">On the **General** page of the **Create Device Collection Wizard**, enter a name for the collection.</span></span>

5. <span data-ttu-id="e1dd8-150">Wählen **Durchsuchen** aus, um eine begrenzende Sammlung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-150">Choose **Browse** to specify a limiting collection.</span></span>

6. <span data-ttu-id="e1dd8-151">Wählen Sie auf der Seite **Mitgliedschaftsregeln** die Option **Regel hinzufügen** aus, und wählen Sie dann **Direkte Regel** aus, um den **Assistent für die Erstellung von Regeln der direkten Mitgliedschaft** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-151">On the **Membership Rules** page, choose **Add Rule**, and then choose **Direct Rule** to open the **Create Direct Membership Rule Wizard**.</span></span> <span data-ttu-id="e1dd8-152">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-152">Choose **Next**.</span></span>

7. <span data-ttu-id="e1dd8-153">Wählen Sie auf der Seite **Ressourcen suchen** in der Liste **Ressourcenklasse** die Option **Systemressource** aus.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-153">On the **Search for Resources** page, in the **Resource class** list, choose **System Resource**.</span></span> <span data-ttu-id="e1dd8-154">Wählen Sie in der Liste **Attributname** die Option **Name** aus.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-154">In the **Attribute name** list, choose **Name**.</span></span> <span data-ttu-id="e1dd8-155">Geben Sie im Feld **Wert** das Zeichen `%` ein, und wählen Sie dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-155">In the **Value** field, enter `%`, and then choose **Next**.</span></span>

8. <span data-ttu-id="e1dd8-156">Aktivieren Sie auf der Seite **Ressourcen auswählen** das Kontrollkästchen für jeden Computer, für den Sie .NET Framework bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-156">On the **Select Resources** page, select the check box for each computer that you want to deploy the .NET Framework to.</span></span> <span data-ttu-id="e1dd8-157">Wählen Sie **Weiter** aus, und schließen Sie den Assistenten.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-157">Choose **Next**, and then complete the wizard.</span></span>

9. <span data-ttu-id="e1dd8-158">Wählen Sie auf der Seite **Mitgliedschaftsregeln** im **Assistent zum Erstellen von Gerätesammlungen** die Option **Weiter** aus, und schließen Sie den Assistenten ab.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-158">On the **Membership Rules** page of the **Create Device Collection Wizard**, choose **Next**, and then complete the wizard.</span></span>

<a name="creating_a_package"></a>

### <a name="create-a-package-and-program-for-the-net-framework-redistributable-package"></a><span data-ttu-id="e1dd8-159">Erstellen eines Pakets und Programms für das verteilbare .NET Framework-Paket</span><span class="sxs-lookup"><span data-stu-id="e1dd8-159">Create a package and program for the .NET Framework redistributable package</span></span>

<span data-ttu-id="e1dd8-160">Mit den folgenden Schritten erstellen Sie manuell ein Paket für das verteilbare .NET Framework-Paket.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-160">The following steps create a package for the .NET Framework redistributable manually.</span></span> <span data-ttu-id="e1dd8-161">Das Paket enthält die angegebenen Parameter zum Installieren des .NET Framework und zu dem Speicherort, von dem das Paket an die Zielcomputer verteilt wird.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-161">The package contains the specified parameters for installing .NET Framework and the location from where the package will be distributed to the target computers.</span></span>

<span data-ttu-id="e1dd8-162">So erstellen Sie ein Paket</span><span class="sxs-lookup"><span data-stu-id="e1dd8-162">To create a package:</span></span>

1. <span data-ttu-id="e1dd8-163">Wählen Sie in der Configuration Manager-Konsole **Softwarebibliothek** aus.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-163">In the Configuration Manager console, choose **Software Library**.</span></span>

2. <span data-ttu-id="e1dd8-164">Erweitern Sie im Arbeitsbereich **Softwarebibliothek** den Knoten **Anwendungsverwaltung**, und wählen Sie dann **Pakete** aus.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-164">In the **Software Library** workspace, expand **Application Management**, and then choose **Packages**.</span></span>

3. <span data-ttu-id="e1dd8-165">Wählen Sie auf der Registerkarte **Startseite** in der Gruppe **Erstellen** die Option **Paket erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-165">On the **Home** tab, in the **Create** group, choose **Create Package**.</span></span>

4. <span data-ttu-id="e1dd8-166">Geben Sie auf der Seite **Paket** im **Assistent zum Erstellen von Paketen und Programmen** die folgenden Informationen ein:</span><span class="sxs-lookup"><span data-stu-id="e1dd8-166">On the **Package** page of the **Create Package and Program Wizard**, enter the following information:</span></span>

    - <span data-ttu-id="e1dd8-167">Name: `.NET Framework 4.5`</span><span class="sxs-lookup"><span data-stu-id="e1dd8-167">Name: `.NET Framework 4.5`</span></span>

    - <span data-ttu-id="e1dd8-168">Hersteller: `Microsoft`</span><span class="sxs-lookup"><span data-stu-id="e1dd8-168">Manufacturer: `Microsoft`</span></span>

    - <span data-ttu-id="e1dd8-169">Sprache:</span><span class="sxs-lookup"><span data-stu-id="e1dd8-169">Language.</span></span> `English (US)`

5. <span data-ttu-id="e1dd8-170">Wählen Sie **Dieses Paket enthält Quelldateien** aus, und wählen Sie anschließend **Durchsuchen** aus, um den lokalen oder Netzwerkordner mit den .NET Framework-Installationsdateien auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-170">Choose **This package contains source files**, and then choose **Browse** to select the local or network folder that contains the .NET Framework installation files.</span></span> <span data-ttu-id="e1dd8-171">Wenn Sie den Ordner ausgewählt haben, wählen Sie **OK** und anschließend **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-171">When you have selected the folder, choose **OK**, and then choose **Next**.</span></span>

6. <span data-ttu-id="e1dd8-172">Wählen Sie auf der Seite **Programmtyp** des Assistenten **Standardprogramm** und anschließend **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-172">On the **Program Type** page of the wizard, choose **Standard Program**, and then choose **Next**.</span></span>

7. <span data-ttu-id="e1dd8-173">Geben Sie auf der Seite **Programm** im **Assistent zum Erstellen von Paketen und Programmen** die folgenden Informationen ein:</span><span class="sxs-lookup"><span data-stu-id="e1dd8-173">On the **Program** page of the **Create Package and Program Wizard**, enter the following information:</span></span>

    1. <span data-ttu-id="e1dd8-174">**Name:** `.NET Framework 4.5`</span><span class="sxs-lookup"><span data-stu-id="e1dd8-174">**Name:** `.NET Framework 4.5`</span></span>

    2. <span data-ttu-id="e1dd8-175">**Befehlszeile:** `dotNetFx45_Full_x86_x64.exe /q /norestart /ChainingPackage ADMINDEPLOYMENT` (Befehlszeilenoptionen werden in der Tabelle weiter unten beschrieben)</span><span class="sxs-lookup"><span data-stu-id="e1dd8-175">**Command line:** `dotNetFx45_Full_x86_x64.exe /q /norestart /ChainingPackage ADMINDEPLOYMENT` (command-line options are described in the table after these steps)</span></span>

    3. <span data-ttu-id="e1dd8-176">**Ausführen:** Wählen Sie **Ausgeblendet** aus.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-176">**Run:** Choose **Hidden**.</span></span>

    4. <span data-ttu-id="e1dd8-177">**Programmausführung:** Wählen Sie die Option aus, die angibt, dass das Programm unabhängig davon, ob ein Benutzer angemeldet ist, ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-177">**Program can run:** Choose the option that specifies that the program can run regardless of whether a user is logged on.</span></span>

8. <span data-ttu-id="e1dd8-178">Wählen Sie auf der Seite **Anforderungen** zum Übernehmen der Standardwerte **Weiter** aus, und schließen Sie dann den Assistenten ab.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-178">On the **Requirements** page, choose **Next** to accept the default values, and then complete the wizard.</span></span>

<span data-ttu-id="e1dd8-179">In der folgenden Tabelle werden die in Schritt 7 angegebenen Befehlszeilenoptionen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-179">The following table describes the command-line options specified in step 7.</span></span>

|<span data-ttu-id="e1dd8-180">Option</span><span class="sxs-lookup"><span data-stu-id="e1dd8-180">Option</span></span>|<span data-ttu-id="e1dd8-181">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e1dd8-181">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="e1dd8-182">**/q**</span><span class="sxs-lookup"><span data-stu-id="e1dd8-182">**/q**</span></span>|<span data-ttu-id="e1dd8-183">Legt den stillen Modus fest.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-183">Sets quiet mode.</span></span> <span data-ttu-id="e1dd8-184">Es sind keine Benutzereingaben erforderlich, und es wird keine Ausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-184">No user input is required, and no output is shown.</span></span>|
|<span data-ttu-id="e1dd8-185">**/norestart**</span><span class="sxs-lookup"><span data-stu-id="e1dd8-185">**/norestart**</span></span>|<span data-ttu-id="e1dd8-186">Verhindert, dass das Setupprogramm automatisch erneut gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-186">Prevents the Setup program from rebooting automatically.</span></span> <span data-ttu-id="e1dd8-187">Bei Verwendung dieser Option muss Configuration Manager den Neustart des Computers behandeln.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-187">If you use this option, Configuration Manager must handle the computer restart.</span></span>|
|<span data-ttu-id="e1dd8-188">**/chainingpackage** *PackageName*</span><span class="sxs-lookup"><span data-stu-id="e1dd8-188">**/chainingpackage** *PackageName*</span></span>|<span data-ttu-id="e1dd8-189">Gibt den Namen des Pakets an, das das Verketten ausführt.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-189">Specifies the name of the package that is doing the chaining.</span></span> <span data-ttu-id="e1dd8-190">Diese Informationen werden zusammen mit anderen Installationssitzungsinformationen für Personen ausgegeben, die sich beim Microsoft-Programm zur Verbesserung der Benutzerfreundlichkeit (Customer Experience Improvement Program, CEIP) registriert haben.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-190">This information is reported with other installation session information for those who have signed up for the Microsoft Customer Experience Improvement Program (CEIP).</span></span> <span data-ttu-id="e1dd8-191">Wenn der Paketname Leerzeichen enthält, verwenden Sie als Trennzeichen doppelte Anführungszeichen, z.B. **/chainingpackage "Chaining Product"** .</span><span class="sxs-lookup"><span data-stu-id="e1dd8-191">If the package name includes spaces, use double quotation marks as delimiters; for example: **/chainingpackage "Chaining Product"**.</span></span>|

<span data-ttu-id="e1dd8-192">Mit diesen Schritten wird ein Paket namens ".NET Framework 4.5" erstellt.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-192">These steps create a package named .NET Framework 4.5.</span></span> <span data-ttu-id="e1dd8-193">Das Programm stellt eine automatische Installation von .NET Framework 4.5 bereit.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-193">The program deploys a silent installation of .NET Framework 4.5.</span></span> <span data-ttu-id="e1dd8-194">In einer automatischen Installation greifen Benutzer nicht in den Installationsvorgang ein, und die Verkettungsanwendung muss den Rückgabecode erfassen und den Neustart initiieren. Weitere Informationen finden Sie in der unter [Getting Progress Information from an Installation Package (Abrufen von Statusinformationen aus einem Installationspaket)](/previous-versions/cc825975(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="e1dd8-194">In a silent installation, users do not interact with the installation process, and the chaining application has to capture the return code and handle rebooting; see [Getting Progress Information from an Installation Package](/previous-versions/cc825975(v=vs.100)).</span></span>

<a name="select_dist_point"></a>

### <a name="select-a-distribution-point"></a><span data-ttu-id="e1dd8-195">Auswählen eines Verteilungspunkts</span><span class="sxs-lookup"><span data-stu-id="e1dd8-195">Select a distribution point</span></span>

<span data-ttu-id="e1dd8-196">Um das Paket und Programm von einem Server an Clientcomputer zu verteilen, müssen Sie zuerst ein Standortsystem als Verteilungspunkt festlegen und das Paket dann an den Verteilungspunkt verteilen.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-196">To distribute the package and program to client computers from a server, you must first designate a site system as a distribution point and then distribute the package to the distribution point.</span></span>

<span data-ttu-id="e1dd8-197">Führen Sie die folgenden Schritte aus, um einen Verteilungspunkt für das im vorherigen Abschnitt erstellte .NET Framework 4.5-Paket auszuwählen:</span><span class="sxs-lookup"><span data-stu-id="e1dd8-197">Use the following steps to select a distribution point for the .NET Framework 4.5 package you created in the previous section:</span></span>

1. <span data-ttu-id="e1dd8-198">Wählen Sie in der Configuration Manager-Konsole **Softwarebibliothek** aus.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-198">In the Configuration Manager console, choose **Software Library**.</span></span>

2. <span data-ttu-id="e1dd8-199">Erweitern Sie im Arbeitsbereich **Softwarebibliothek** den Knoten **Anwendungsverwaltung**, und wählen Sie dann **Pakete** aus.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-199">In the **Software Library** workspace, expand **Application Management**, and then choose **Packages**.</span></span>

3. <span data-ttu-id="e1dd8-200">Wählen Sie aus der Liste von Paketen das Paket **.NET Framework 4.5** aus, das Sie im vorherigen Abschnitt erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-200">From the list of packages, select the package **.NET Framework 4.5** that you created in the previous section.</span></span>

4. <span data-ttu-id="e1dd8-201">Wählen Sie auf der Registerkarte **Startseite** in der Gruppe **Bereitstellung** die Option **Inhalt verteilen** aus.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-201">On the **Home** tab, in the **Deployment** group, choose **Distribute Content**.</span></span>

5. <span data-ttu-id="e1dd8-202">Wählen Sie auf der Registerkarte **Allgemein** im **Assistent für die Verteilung von Inhalt** die Option **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-202">On the **General** tab of the **Distribute Content Wizard**, choose **Next**.</span></span>

6. <span data-ttu-id="e1dd8-203">Wählen Sie auf der Seite **Inhaltsziel** des Assistenten **Hinzufügen** und anschließend **Verteilungspunkt** aus.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-203">On the **Content Destination** page of the wizard, choose **Add**, and then choose **Distribution Point**.</span></span>

7. <span data-ttu-id="e1dd8-204">Wählen Sie im Dialogfeld **Verteilungspunkte hinzufügen** mindestens einen Verteilungspunkt aus, von dem das Paket und Programm gehostet werden sollen, und wählen Sie dann **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-204">In the **Add Distribution Points** dialog box, select the distribution point(s) that will host the package and program, and then choose **OK**.</span></span>

8. <span data-ttu-id="e1dd8-205">Durchlaufen Sie den Assistenten.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-205">Complete the wizard.</span></span>

<span data-ttu-id="e1dd8-206">Das Paket enthält jetzt alle Informationen, die Sie für die automatische Bereitstellung von .NET Framework 4.5 benötigen.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-206">The package now contains all the information you need to silently deploy .NET Framework 4.5.</span></span> <span data-ttu-id="e1dd8-207">Überprüfen Sie vor dem Bereitstellen des Pakets und Programms, ob die Installation auf dem Verteilungspunkt ausgeführt wurde. Weitere Informationen finden Sie im Abschnitt „Überwachen des Inhaltsstatus“ unter [Überwachen von mit Configuration Manager verteilten Inhalten](/configmgr/core/servers/deploy/configure/monitor-content-you-have-distributed) in der Configuration Manager-Dokumentationsbibliothek.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-207">Before you deploy the package and program, verify that it was installed on the distribution point; see the "Content status monitoring" section of [Monitor content you distribute with Configuration Manager](/configmgr/core/servers/deploy/configure/monitor-content-you-have-distributed) in the Configuration Manager Documentation Library.</span></span>

<a name="deploying_package"></a>

### <a name="deploy-the-package"></a><span data-ttu-id="e1dd8-208">Bereitstellen des Pakets</span><span class="sxs-lookup"><span data-stu-id="e1dd8-208">Deploy the package</span></span>

<span data-ttu-id="e1dd8-209">So stellen Sie das .NET Framework 4.5-Paket und -Programm bereit</span><span class="sxs-lookup"><span data-stu-id="e1dd8-209">To deploy the .NET Framework 4.5 package and program:</span></span>

1. <span data-ttu-id="e1dd8-210">Wählen Sie in der Configuration Manager-Konsole **Softwarebibliothek** aus.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-210">In the Configuration Manager console, choose **Software Library**.</span></span>

2. <span data-ttu-id="e1dd8-211">Erweitern Sie im Arbeitsbereich **Softwarebibliothek** den Knoten **Anwendungsverwaltung**, und wählen Sie dann **Pakete** aus.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-211">In the **Software Library** workspace, expand **Application Management**, and then choose **Packages**.</span></span>

3. <span data-ttu-id="e1dd8-212">Wählen Sie aus der Liste von Paketen das Paket **.NET Framework 4.5** aus, das Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-212">From the list of packages, select the package you created named **.NET Framework 4.5**.</span></span>

4. <span data-ttu-id="e1dd8-213">Wählen Sie auf der Registerkarte **Startseite** in der Gruppe **Bereitstellung** die Option **Bereitstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-213">On the **Home** tab, in the **Deployment** group, choose **Deploy**.</span></span>

5. <span data-ttu-id="e1dd8-214">Wählen Sie auf der Seite **Allgemein** im **Assistent zum Bereitstellen von Software** die Option **Durchsuchen** und anschließend die Sammlung aus, die Sie zuvor erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-214">On the **General** page of the **Deploy Software Wizard**, choose **Browse**, and then select the collection that you created earlier.</span></span> <span data-ttu-id="e1dd8-215">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-215">Choose **Next**.</span></span>

6. <span data-ttu-id="e1dd8-216">Überprüfen Sie auf der Seite **Inhalt** des Assistenten, ob der Punkt, von dem Sie die Software verteilen möchten, angezeigt wird. Wählen Sie anschließend **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-216">On the **Content** page of the wizard, verify that the point from which you want to distribute the software is displayed, and then choose **Next**.</span></span>

7. <span data-ttu-id="e1dd8-217">Bestätigen Sie auf der Seite **Bereitstellungseinstellungen** des Assistenten, dass **Aktion** auf **Installieren** festgelegt ist und dass **Zweck** auf **Erforderlich** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-217">On the **Deployment Settings** page of the wizard, confirm that **Action** is set to **Install**, and **Purpose** is set to **Required**.</span></span> <span data-ttu-id="e1dd8-218">Dadurch wird sichergestellt, dass die Installation des Softwarepakets auf den Zielcomputern erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-218">This ensures that the software package will be a mandatory installation on the targeted computers.</span></span> <span data-ttu-id="e1dd8-219">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-219">Choose **Next**.</span></span>

8. <span data-ttu-id="e1dd8-220">Geben Sie auf der Seite **Zeitplanung** des Assistenten an, wann das .NET Framework installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-220">On the **Scheduling** page of the wizard, specify when you want .NET Framework to be installed.</span></span> <span data-ttu-id="e1dd8-221">Sie können **Neu** auswählen, um eine Installationszeit zuzuweisen, oder die Software anweisen, die Installation bei An- oder Abmeldung des Benutzers oder so schnell wie möglich durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-221">You can choose **New** to assign an installation time, or instruct the software to install when the user logs on or off, or as soon as possible.</span></span> <span data-ttu-id="e1dd8-222">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-222">Choose **Next**.</span></span>

9. <span data-ttu-id="e1dd8-223">Verwenden Sie auf der Seite **Benutzerfreundlichkeit** des Assistenten die Standardwerte, und wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-223">On the **User Experience** page of the wizard, use the default values and choose **Next**.</span></span>

    > [!WARNING]
    > <span data-ttu-id="e1dd8-224">Möglicherweise gelten in Ihrer Produktionsumgebung Richtlinien, die eine andere Auswahl für den Bereitstellungszeitplan erfordern.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-224">Your production environment might have policies that require different selections for the deployment schedule.</span></span>

10. <span data-ttu-id="e1dd8-225">Verwenden Sie auf der Seite **Verteilungspunkte** des Assistenten die Standardwerte, und wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-225">On the **Distribution Points** page of the wizard, use the default values and choose **Next**.</span></span>

11. <span data-ttu-id="e1dd8-226">Durchlaufen Sie den Assistenten.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-226">Complete the wizard.</span></span> <span data-ttu-id="e1dd8-227">Sie können den Status der Bereitstellung im Knoten **Bereitstellungen** des Arbeitsbereichs **Überwachung** überwachen.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-227">You can monitor the progress of the deployment in the **Deployments** node of the **Monitoring** workspace.</span></span>

<span data-ttu-id="e1dd8-228">Das Paket wird nun in der als Ziel festgelegten Sammlung bereitgestellt, und die automatische Installation von .NET Framework 4.5 beginnt.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-228">The package will now be deployed to the targeted collection and the silent installation of .NET Framework 4.5 will begin.</span></span> <span data-ttu-id="e1dd8-229">Informationen zu Fehlercodes für die .NET Framework 4.5-Installation finden Sie weiter unten in diesem Thema im Abschnitt [Rückgabecodes](#return_codes).</span><span class="sxs-lookup"><span data-stu-id="e1dd8-229">For information about .NET Framework 4.5 installation error codes, see the [Return Codes](#return_codes) section later in this topic.</span></span>

<a name="resources"></a>

## <a name="resources"></a><span data-ttu-id="e1dd8-230">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="e1dd8-230">Resources</span></span>

<span data-ttu-id="e1dd8-231">Weitere Informationen zur Infrastruktur zum Testen der Bereitstellung des weitervertreibbaren .NET Framework 4.5-Pakets finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="e1dd8-231">For more information about the infrastructure for testing the deployment of the .NET Framework 4.5 redistributable package, see the following resources.</span></span>

<span data-ttu-id="e1dd8-232">**Active Directory, DNS, DHCP:**</span><span class="sxs-lookup"><span data-stu-id="e1dd8-232">**Active Directory, DNS, DHCP:**</span></span>

- [<span data-ttu-id="e1dd8-233">Active Directory Domain Services</span><span class="sxs-lookup"><span data-stu-id="e1dd8-233">Active Directory Domain Services</span></span>](/windows/desktop/ad/active-directory-domain-services)

- [<span data-ttu-id="e1dd8-234">Domain Name System (DNS)</span><span class="sxs-lookup"><span data-stu-id="e1dd8-234">Domain Name System (DNS)</span></span>](/windows-server/networking/dns/dns-top)

- [<span data-ttu-id="e1dd8-235">Dynamic Host Configuration-Protokoll (DHCP)</span><span class="sxs-lookup"><span data-stu-id="e1dd8-235">Dynamic Host Configuration Protocol (DHCP)</span></span>](/windows-server/networking/technologies/dhcp/dhcp-top)

<span data-ttu-id="e1dd8-236">**SQL Server 2008:**</span><span class="sxs-lookup"><span data-stu-id="e1dd8-236">**SQL Server 2008:**</span></span>

- <span data-ttu-id="e1dd8-237">[Installieren von SQL Server 2008 (SQL Server-Video)](/previous-versions/sql/sql-server-2008/dd299415(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="e1dd8-237">[Installing SQL Server 2008 (SQL Server Video)](/previous-versions/sql/sql-server-2008/dd299415(v=sql.100))</span></span>

- [<span data-ttu-id="e1dd8-238">SQL Server 2008-Sicherheit: Übersicht für Datenbankadministratoren</span><span class="sxs-lookup"><span data-stu-id="e1dd8-238">SQL Server 2008 Security Overview for Database Administrators</span></span>](https://download.microsoft.com/download/a/c/d/acd8e043-d69b-4f09-bc9e-4168b65aaa71/SQL2008SecurityOverviewforAdmins.docx)

<span data-ttu-id="e1dd8-239">**System Center 2012 Configuration Manager (Verwaltungspunkt, Verteilungspunkt):**</span><span class="sxs-lookup"><span data-stu-id="e1dd8-239">**System Center 2012 Configuration Manager (Management Point, Distribution Point):**</span></span>

- <span data-ttu-id="e1dd8-240">[Standortverwaltung für System Center 2012 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg681983(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="e1dd8-240">[Site Administration for System Center 2012 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg681983(v=technet.10))</span></span>

<span data-ttu-id="e1dd8-241">**System Center 2012 Configuration Manager-Client für Windows-Computer:**</span><span class="sxs-lookup"><span data-stu-id="e1dd8-241">**System Center 2012 Configuration Manager client for Windows computers:**</span></span>

- <span data-ttu-id="e1dd8-242">[Bereitstellen von Clients für System Center 2012 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699391(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="e1dd8-242">[Deploying Clients for System Center 2012 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699391(v=technet.10))</span></span>

<a name="troubleshooting"></a>

## <a name="troubleshooting"></a><span data-ttu-id="e1dd8-243">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="e1dd8-243">Troubleshooting</span></span>

### <a name="log-file-locations"></a><span data-ttu-id="e1dd8-244">Protokolldateispeicherorte</span><span class="sxs-lookup"><span data-stu-id="e1dd8-244">Log file locations</span></span>

<span data-ttu-id="e1dd8-245">Beim Setup von .NET Framework werden die folgenden Protokolldateien generiert:</span><span class="sxs-lookup"><span data-stu-id="e1dd8-245">The following log files are generated during .NET Framework setup:</span></span>

- <span data-ttu-id="e1dd8-246">%temp%\Microsoft .NET Framework *version*\*.txt</span><span class="sxs-lookup"><span data-stu-id="e1dd8-246">%temp%\Microsoft .NET Framework *version*\*.txt</span></span>
- <span data-ttu-id="e1dd8-247">%temp%\Microsoft .NET Framework *version*\*.html,</span><span class="sxs-lookup"><span data-stu-id="e1dd8-247">%temp%\Microsoft .NET Framework *version*\*.html</span></span>

<span data-ttu-id="e1dd8-248">wobei *version* der .NET Framework-Version entspricht, die Sie installieren (z. B. 4.5 oder 4.7.2).</span><span class="sxs-lookup"><span data-stu-id="e1dd8-248">where *version* is the version of .NET Framework that you're installing, such as 4.5 or 4.7.2.</span></span>

<span data-ttu-id="e1dd8-249">Sie können ebenso das Verzeichnis angeben, in das Protokolldateien geschrieben werden. Verwenden Sie hierzu die Befehlszeilenoption `/log` im Installationsbefehl von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-249">You can also specify the directory to which log files are written by using the `/log` command-line option in the .NET Framework installation command.</span></span> <span data-ttu-id="e1dd8-250">Weitere Informationen finden Sie im [Leitfaden für die Bereitstellung von .NET Framework für Entwickler](deployment-guide-for-developers.md#command-line-options).</span><span class="sxs-lookup"><span data-stu-id="e1dd8-250">For more information, see [.NET Framework deployment guide for developers](deployment-guide-for-developers.md#command-line-options).</span></span>

<span data-ttu-id="e1dd8-251">Mit dem [Protokollerfassungstool (Log Collection Tool)](https://www.microsoft.com/download/details.aspx?id=12493) können Sie die .NET Framework-Protokolldateien erfassen und eine komprimierte CAB-Datei erstellen, um die Größe der Dateien zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-251">You can use the [log collection tool](https://www.microsoft.com/download/details.aspx?id=12493) to collect the .NET Framework log files and to create a compressed cabinet (.cab) file that reduces the size of the files.</span></span>

<a name="return_codes"></a>

### <a name="return-codes"></a><span data-ttu-id="e1dd8-252">Rückgabecodes</span><span class="sxs-lookup"><span data-stu-id="e1dd8-252">Return codes</span></span>

<span data-ttu-id="e1dd8-253">Die folgende Tabelle enthält die gängigsten Rückgabecodes des weitervertreibbaren .NET Framework 4.5-Installationsprogramms.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-253">The following table lists the most common return codes from the .NET Framework 4.5 redistributable installation program.</span></span> <span data-ttu-id="e1dd8-254">Die Rückgabecodes sind für alle Versionen des Installationsprogramms identisch.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-254">The return codes are the same for all versions of the installer.</span></span>

<span data-ttu-id="e1dd8-255">Links zu ausführlichen Informationen finden Sie im nächsten Abschnitt [Downloadfehlercodes](#additional_error_codes).</span><span class="sxs-lookup"><span data-stu-id="e1dd8-255">For links to detailed information, see the next section, [Download error codes](#additional_error_codes).</span></span>

|<span data-ttu-id="e1dd8-256">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="e1dd8-256">Return code</span></span>|<span data-ttu-id="e1dd8-257">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e1dd8-257">Description</span></span>|
|-----------------|-----------------|
|<span data-ttu-id="e1dd8-258">0</span><span class="sxs-lookup"><span data-stu-id="e1dd8-258">0</span></span>|<span data-ttu-id="e1dd8-259">Die Installation wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-259">Installation completed successfully.</span></span>|
|<span data-ttu-id="e1dd8-260">1602</span><span class="sxs-lookup"><span data-stu-id="e1dd8-260">1602</span></span>|<span data-ttu-id="e1dd8-261">Der Benutzer hat die Installation abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-261">The user canceled installation.</span></span>|
|<span data-ttu-id="e1dd8-262">1603</span><span class="sxs-lookup"><span data-stu-id="e1dd8-262">1603</span></span>|<span data-ttu-id="e1dd8-263">Während der Installation ist ein schwerwiegender Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-263">A fatal error occurred during installation.</span></span>|
|<span data-ttu-id="e1dd8-264">1641</span><span class="sxs-lookup"><span data-stu-id="e1dd8-264">1641</span></span>|<span data-ttu-id="e1dd8-265">Ein Neustart ist erforderlich, um die Installation abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-265">A restart is required to complete the installation.</span></span> <span data-ttu-id="e1dd8-266">Diese Meldung zeigt eine erfolgreiche Installation an.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-266">This message indicates success.</span></span>|
|<span data-ttu-id="e1dd8-267">3010</span><span class="sxs-lookup"><span data-stu-id="e1dd8-267">3010</span></span>|<span data-ttu-id="e1dd8-268">Ein Neustart ist erforderlich, um die Installation abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-268">A restart is required to complete the installation.</span></span> <span data-ttu-id="e1dd8-269">Diese Meldung zeigt eine erfolgreiche Installation an.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-269">This message indicates success.</span></span>|
|<span data-ttu-id="e1dd8-270">5100</span><span class="sxs-lookup"><span data-stu-id="e1dd8-270">5100</span></span>|<span data-ttu-id="e1dd8-271">Der Computer des Benutzers erfüllt die Systemanforderungen nicht.</span><span class="sxs-lookup"><span data-stu-id="e1dd8-271">The user's computer does not meet system requirements.</span></span>|

<a name="additional_error_codes"></a>

### <a name="download-error-codes"></a><span data-ttu-id="e1dd8-272">Downloadfehlercodes</span><span class="sxs-lookup"><span data-stu-id="e1dd8-272">Download error codes</span></span>

- [<span data-ttu-id="e1dd8-273">Fehlercodes für BITS (Background Intelligent Transfer Service)</span><span class="sxs-lookup"><span data-stu-id="e1dd8-273">Background Intelligent Transfer Service (BITS) error codes</span></span>](/windows/desktop/Bits/bits-return-values)

- <span data-ttu-id="e1dd8-274">[Fehlercodes für URL-Moniker](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms775145(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="e1dd8-274">[URL moniker error codes](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms775145(v=vs.85))</span></span>

- [<span data-ttu-id="e1dd8-275">Fehlercodes für WinHttp</span><span class="sxs-lookup"><span data-stu-id="e1dd8-275">WinHttp error codes</span></span>](/windows/desktop/WinHttp/error-messages)

<span data-ttu-id="e1dd8-276">Sonstige Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="e1dd8-276">Other error codes:</span></span>

- [<span data-ttu-id="e1dd8-277">Fehlercodes für Windows Installer</span><span class="sxs-lookup"><span data-stu-id="e1dd8-277">Windows Installer error codes</span></span>](/windows/desktop/msi/error-codes)

- <span data-ttu-id="e1dd8-278">[Ergebniscodes für Windows Update Agent](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc720442(v=ws.10))</span><span class="sxs-lookup"><span data-stu-id="e1dd8-278">[Windows Update Agent result codes](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc720442(v=ws.10))</span></span>

## <a name="see-also"></a><span data-ttu-id="e1dd8-279">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e1dd8-279">See also</span></span>

- [<span data-ttu-id="e1dd8-280">Bereitstellungshandbuch für Entwickler</span><span class="sxs-lookup"><span data-stu-id="e1dd8-280">Deployment Guide for Developers</span></span>](deployment-guide-for-developers.md)
- [<span data-ttu-id="e1dd8-281">Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="e1dd8-281">System Requirements</span></span>](../get-started/system-requirements.md)
