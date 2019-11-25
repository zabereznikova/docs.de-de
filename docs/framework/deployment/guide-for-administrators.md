---
title: Handbuch für die Bereitstellung von .NET Framework für Administratoren
ms.date: 04/10/2018
helpviewer_keywords:
- administrator's guide, deploying .NET Framework
- deployment [.NET Framework], administrator's guide
ms.assetid: bee14036-0436-44e8-89f5-4bc61317977a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dc842713a16df8e5ada5ad6c71ca19f91ecbc405
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975571"
---
# <a name="net-framework-deployment-guide-for-administrators"></a><span data-ttu-id="f9801-102">Handbuch für die Bereitstellung von .NET Framework für Administratoren</span><span class="sxs-lookup"><span data-stu-id="f9801-102">.NET Framework Deployment Guide for Administrators</span></span>

<span data-ttu-id="f9801-103">In diesem Artikel erfahren Sie Schritt für Schritt, wie Systemadministratoren .NET Framework 4.5 und dessen Systemabhängigkeiten in einem Netzwerk mit Microsoft System Center Configuration Manager bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="f9801-103">This step-by-step article describes how a system administrator can deploy the .NET Framework 4.5 and its system dependencies across a network by using Microsoft System Center Configuration Manager.</span></span> <span data-ttu-id="f9801-104">In diesem Artikel wird davon ausgegangen, dass alle Zielclientcomputer die Mindestanforderungen für .NET Framework erfüllen.</span><span class="sxs-lookup"><span data-stu-id="f9801-104">This article assumes that all target client computers meet the minimum requirements for the .NET Framework.</span></span> <span data-ttu-id="f9801-105">Eine Liste mit den Software- und Hardwareanforderungen für die Installation von .NET Framework 4.5 finden Sie unter [Systemanforderungen für .NET Framework](../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9801-105">For a list of the software and hardware requirements for installing the .NET Framework 4.5, see [System Requirements](../get-started/system-requirements.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f9801-106">Die Software, auf die in diesem Dokument verwiesen wird (einschließlich .NET Framework 4.5, System Center Configuration Manager und Active Directory), unterliegt jeweils den geltenden Lizenzbedingungen.</span><span class="sxs-lookup"><span data-stu-id="f9801-106">The software referenced in this document, including, without limitation, the .NET Framework 4.5, System Center Configuration Manager, and Active Directory, are each subject to license terms and conditions.</span></span> <span data-ttu-id="f9801-107">In diesen Anweisungen wird vorausgesetzt, dass die Lizenzbestimmungen von den entsprechenden Lizenznehmern der Software gelesen und akzeptiert wurden.</span><span class="sxs-lookup"><span data-stu-id="f9801-107">These instructions assume that such license terms and conditions have been reviewed and accepted by the appropriate licensees of the software.</span></span> <span data-ttu-id="f9801-108">Diese Anweisungen bedeuten keinen Verzicht auf die Bestimmungen von Lizenzvereinbarungen.</span><span class="sxs-lookup"><span data-stu-id="f9801-108">These instructions do not waive any of the terms and conditions of such license agreements.</span></span>
>
> <span data-ttu-id="f9801-109">Informationen zur Unterstützung für .NET Framework finden Sie unter [.NET Framework Support-Richtlinie](https://dotnet.microsoft.com/platform/support/policy/dotnet-framework) auf der Microsoft Support-Website.</span><span class="sxs-lookup"><span data-stu-id="f9801-109">For information about support for the .NET Framework, see [.NET Framework official support policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-framework) on the Microsoft Support website.</span></span>

<span data-ttu-id="f9801-110">Dieses Thema enthält folgende Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="f9801-110">This topic contains the following sections:</span></span>

- [<span data-ttu-id="f9801-111">Bereitstellungsprozess</span><span class="sxs-lookup"><span data-stu-id="f9801-111">The deployment process</span></span>](#the_deployment_process)
- [<span data-ttu-id="f9801-112">Bereitstellen von .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f9801-112">Deploying the .NET Framework</span></span>](#deploying_in_a_test_environment)
- [<span data-ttu-id="f9801-113">Erstellen einer Sammlung</span><span class="sxs-lookup"><span data-stu-id="f9801-113">Create a collection</span></span>](#creating_a_collection)
- [<span data-ttu-id="f9801-114">Erstellen eines Pakets und Programms</span><span class="sxs-lookup"><span data-stu-id="f9801-114">Create a package and program</span></span>](#creating_a_package)
- [<span data-ttu-id="f9801-115">Auswählen eines Verteilungspunkts</span><span class="sxs-lookup"><span data-stu-id="f9801-115">Select a distribution point</span></span>](#select_dist_point)
- [<span data-ttu-id="f9801-116">Bereitstellen des Pakets</span><span class="sxs-lookup"><span data-stu-id="f9801-116">Deploy the package</span></span>](#deploying_package)
- [<span data-ttu-id="f9801-117">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="f9801-117">Resources</span></span>](#resources)
- [<span data-ttu-id="f9801-118">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="f9801-118">Troubleshooting</span></span>](#troubleshooting)

<a name="the_deployment_process"></a>

## <a name="the-deployment-process"></a><span data-ttu-id="f9801-119">Bereitstellungsprozess</span><span class="sxs-lookup"><span data-stu-id="f9801-119">The deployment process</span></span>

<span data-ttu-id="f9801-120">Wenn Sie die unterstützende Infrastruktur eingerichtet haben, stellen Sie das verteilbare .NET Framework-Paket mit System Center 2012 Configuration Manager auf Computern im Netzwerk bereit.</span><span class="sxs-lookup"><span data-stu-id="f9801-120">When you have the supporting infrastructure in place, you use System Center 2012 Configuration Manager to deploy the .NET Framework redistributable package to computers on the network.</span></span> <span data-ttu-id="f9801-121">Der Aufbau der Infrastruktur umfasst das Erstellen und Definieren von fünf primären Bereichen: Sammlungen, ein Paket und ein Programm für die Software, Verteilungspunkte und Bereitstellungen.</span><span class="sxs-lookup"><span data-stu-id="f9801-121">Building the infrastructure involves creating and defining five primary areas: collections, a package and program for the software, distribution points, and deployments.</span></span>

- <span data-ttu-id="f9801-122">Bei **Sammlungen** handelt es sich um Gruppen von Configuration Manager-Ressourcen, z.B. Benutzer, Benutzergruppen oder Computer, für die das .NET Framework bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="f9801-122">**Collections** are groups of Configuration Manager resources, such as users, user groups, or computers, to which the .NET Framework is deployed.</span></span> <span data-ttu-id="f9801-123">Weitere Informationen finden Sie in der Configuration Manager-Dokumentationsbibliothek unter [Einführung in Sammlungen in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/clients/manage/collections/introduction-to-collections).</span><span class="sxs-lookup"><span data-stu-id="f9801-123">For more information, see [Introduction to collections in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/clients/manage/collections/introduction-to-collections) in the Configuration Manager documentation library.</span></span>

- <span data-ttu-id="f9801-124">**Pakete und Programme** stellen in der Regel Softwareanwendungen dar, die auf einem Clientcomputer installiert werden, sie können jedoch auch einzelne Dateien, Updates oder sogar einzelne Befehle enthalten.</span><span class="sxs-lookup"><span data-stu-id="f9801-124">**Packages and programs** typically represent software applications to be installed on a client computer, but they might also contain individual files, updates, or even individual commands.</span></span> <span data-ttu-id="f9801-125">Weitere Informationen finden Sie in der Configuration Manager-Dokumentationsbibliothek unter [Pakete und Programme in System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).</span><span class="sxs-lookup"><span data-stu-id="f9801-125">For more information, see [Packages and programs in System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs) in the Configuration Manager documentation library.</span></span>

- <span data-ttu-id="f9801-126">**Verteilungspunkte** sind Configuration Manager-Standortsystemrollen, die zum Ausführen von Software auf Clientcomputern erforderliche Dateien speichern.</span><span class="sxs-lookup"><span data-stu-id="f9801-126">**Distribution points** are Configuration Manager site system roles that store files required for software to run on client computers.</span></span> <span data-ttu-id="f9801-127">Wenn der Configuration Manager-Client eine Softwarebereitstellung empfängt und verarbeitet, stellt er eine Verbindung mit einem Verteilungspunkt her, um den mit der Software verbundenen Inhalt herunterzuladen und den Installationsvorgang zu starten.</span><span class="sxs-lookup"><span data-stu-id="f9801-127">When the Configuration Manager client receives and processes a software deployment, it contacts a distribution point to download the content associated with the software and to start the installation process.</span></span> <span data-ttu-id="f9801-128">Weitere Informationen finden Sie in der Configuration Manager-Dokumentationsbibliothek unter [Grundlegende Konzepte für die Inhaltsverwaltung in Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/fundamental-concepts-for-content-management).</span><span class="sxs-lookup"><span data-stu-id="f9801-128">For more information, see [Fundamental concepts for content management in Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/fundamental-concepts-for-content-management) in the Configuration Manager documentation library.</span></span>

- <span data-ttu-id="f9801-129">**Bereitstellungen** weisen zutreffende Member der angegebenen Zielsammlung an, das Softwarepaket zu installieren.</span><span class="sxs-lookup"><span data-stu-id="f9801-129">**Deployments** instruct applicable members of the specified target collection to install the software package.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f9801-130">Die Prozeduren in diesem Thema enthalten typische Einstellungen für das Erstellen und Bereitstellen eines Pakets und Programms und umfassen möglicherweise nicht alle möglichen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="f9801-130">The procedures in this topic contain typical settings for creating and deploying a package and program, and might not cover all possible settings.</span></span> <span data-ttu-id="f9801-131">Weitere Bereitstellungsoptionen im Configuration Manager finden Sie in der [Dokumentationsbibliothek zum Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682041%28v=technet.10%29).</span><span class="sxs-lookup"><span data-stu-id="f9801-131">For other Configuration Manager deployment options, see the [Configuration Manager Documentation Library](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682041%28v=technet.10%29).</span></span>

<a name="deploying_in_a_test_environment"></a>

## <a name="deploying-the-net-framework"></a><span data-ttu-id="f9801-132">Bereitstellen von .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f9801-132">Deploying the .NET Framework</span></span>

<span data-ttu-id="f9801-133">Sie können mit System Center 2012 Configuration Manager eine automatische Installation von .NET Framework 4.5 bereitstellen, bei der die Benutzer nicht in den Installationsvorgang eingreifen.</span><span class="sxs-lookup"><span data-stu-id="f9801-133">You can use System Center 2012 Configuration Manager to deploy a silent installation of the .NET Framework 4.5, where the users do not interact with the installation process.</span></span> <span data-ttu-id="f9801-134">Führen Sie folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="f9801-134">Follow these steps:</span></span>

1. <span data-ttu-id="f9801-135">[Erstellen Sie eine Sammlung](#creating_a_collection).</span><span class="sxs-lookup"><span data-stu-id="f9801-135">[Create a collection](#creating_a_collection).</span></span>

2. <span data-ttu-id="f9801-136">[Erstellen Sie ein Paket und Programm für das verteilbare .NET Framework-Paket](#creating_a_package).</span><span class="sxs-lookup"><span data-stu-id="f9801-136">[Create a package and program for the .NET Framework redistributable](#creating_a_package).</span></span>

3. <span data-ttu-id="f9801-137">[Wählen Sie einen Verteilungspunkt aus](#select_dist_point).</span><span class="sxs-lookup"><span data-stu-id="f9801-137">[Select a distribution point](#select_dist_point).</span></span>

4. <span data-ttu-id="f9801-138">[Stellen Sie das Paket bereit](#deploying_package).</span><span class="sxs-lookup"><span data-stu-id="f9801-138">[Deploy the package](#deploying_package).</span></span>

<a name="creating_a_collection"></a>

### <a name="create-a-collection"></a><span data-ttu-id="f9801-139">Erstellen einer Sammlung</span><span class="sxs-lookup"><span data-stu-id="f9801-139">Create a collection</span></span>

<span data-ttu-id="f9801-140">In diesem Schritt wählen Sie die Computer aus, auf denen Sie das Paket und Programm bereitstellen, und gruppieren sie in einer Gerätesammlung.</span><span class="sxs-lookup"><span data-stu-id="f9801-140">In this step, you select the computers to which you will deploy the package and program, and group them into a device collection.</span></span> <span data-ttu-id="f9801-141">Zum Erstellen einer Sammlung im Configuration Manager können Sie Regeln für die direkte Mitgliedschaft verwenden (wobei Sie die Sammlungsmitglieder manuell angeben). Alternativ können Sie Abfrageregeln verwenden (wobei die Sammlungsmitglieder vom Configuration Manager auf der Grundlage von Kriterien bestimmt werden, die Sie angegeben haben).</span><span class="sxs-lookup"><span data-stu-id="f9801-141">To create a collection in Configuration Manager, you can use direct membership rules (where you manually specify the collection members) or query rules (where Configuration Manager determines the collection members based on criteria you specify).</span></span> <span data-ttu-id="f9801-142">Weitere Informationen zu Mitgliedschaftsregeln, einschließlich abfragebezogenen und direkten Regeln, finden Sie in der Configuration Manager-Dokumentationsbibliothek unter [Einführung in Sammlungen in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/clients/manage/collections/introduction-to-collections).</span><span class="sxs-lookup"><span data-stu-id="f9801-142">For more information about membership rules, including queries and direct rules, see [Introduction to collections in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/clients/manage/collections/introduction-to-collections) in the Configuration Manager Documentation Library.</span></span>

<span data-ttu-id="f9801-143">So erstellen Sie eine Sammlung</span><span class="sxs-lookup"><span data-stu-id="f9801-143">To create a collection:</span></span>

1. <span data-ttu-id="f9801-144">Wählen Sie in der Configuration Manager-Konsole **Bestand und Kompatibilität** aus.</span><span class="sxs-lookup"><span data-stu-id="f9801-144">In the Configuration Manager console, choose **Assets and Compliance**.</span></span>

2. <span data-ttu-id="f9801-145">Wählen Sie im Arbeitsbereich **Bestand und Kompatibilität** die Option **Gerätesammlungen** aus.</span><span class="sxs-lookup"><span data-stu-id="f9801-145">In the **Assets and Compliance** workspace, choose **Device Collections**.</span></span>

3. <span data-ttu-id="f9801-146">Wählen Sie auf der Registerkarte **Startseite** in der Gruppe **Erstellen** die Option **Gerätesammlung erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="f9801-146">On the **Home** tab in the **Create** group, choose **Create Device Collection**.</span></span>

4. <span data-ttu-id="f9801-147">Geben Sie im **Assistent zum Erstellen von Gerätesammlungen** auf der Seite **Allgemein** einen Namen für die Auflistung ein.</span><span class="sxs-lookup"><span data-stu-id="f9801-147">On the **General** page of the **Create Device Collection Wizard**, enter a name for the collection.</span></span>

5. <span data-ttu-id="f9801-148">Wählen **Durchsuchen** aus, um eine begrenzende Sammlung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f9801-148">Choose **Browse** to specify a limiting collection.</span></span>

6. <span data-ttu-id="f9801-149">Wählen Sie auf der Seite **Mitgliedschaftsregeln** die Option **Regel hinzufügen** aus, und wählen Sie dann **Direkte Regel** aus, um den **Assistent für die Erstellung von Regeln der direkten Mitgliedschaft** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f9801-149">On the **Membership Rules** page, choose **Add Rule**, and then choose **Direct Rule** to open the **Create Direct Membership Rule Wizard**.</span></span> <span data-ttu-id="f9801-150">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="f9801-150">Choose **Next**.</span></span>

7. <span data-ttu-id="f9801-151">Wählen Sie auf der Seite **Ressourcen suchen** in der Liste **Ressourcenklasse** die Option **Systemressource** aus.</span><span class="sxs-lookup"><span data-stu-id="f9801-151">On the **Search for Resources** page, in the **Resource class** list, choose **System Resource**.</span></span> <span data-ttu-id="f9801-152">Wählen Sie in der Liste **Attributname** die Option **Name** aus.</span><span class="sxs-lookup"><span data-stu-id="f9801-152">In the **Attribute name** list, choose **Name**.</span></span> <span data-ttu-id="f9801-153">Geben Sie im Feld **Wert** das Zeichen `%` ein, und wählen Sie dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="f9801-153">In the **Value** field, enter `%`, and then choose **Next**.</span></span>

8. <span data-ttu-id="f9801-154">Aktivieren Sie auf der Seite **Ressourcen auswählen** das Kontrollkästchen für jeden Computer, für den Sie .NET Framework bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="f9801-154">On the **Select Resources** page, select the check box for each computer that you want to deploy the .NET Framework to.</span></span> <span data-ttu-id="f9801-155">Wählen Sie **Weiter** aus, und schließen Sie den Assistenten.</span><span class="sxs-lookup"><span data-stu-id="f9801-155">Choose **Next**, and then complete the wizard.</span></span>

9. <span data-ttu-id="f9801-156">Wählen Sie auf der Seite **Mitgliedschaftsregeln** im **Assistent zum Erstellen von Gerätesammlungen** die Option **Weiter** aus, und schließen Sie den Assistenten ab.</span><span class="sxs-lookup"><span data-stu-id="f9801-156">On the **Membership Rules** page of the **Create Device Collection Wizard**, choose **Next**, and then complete the wizard.</span></span>

<a name="creating_a_package"></a>

### <a name="create-a-package-and-program-for-the-net-framework-redistributable-package"></a><span data-ttu-id="f9801-157">Erstellen eines Pakets und Programms für das verteilbare .NET Framework-Paket</span><span class="sxs-lookup"><span data-stu-id="f9801-157">Create a package and program for the .NET Framework redistributable package</span></span>

<span data-ttu-id="f9801-158">Mit den folgenden Schritten erstellen Sie manuell ein Paket für das verteilbare .NET Framework-Paket.</span><span class="sxs-lookup"><span data-stu-id="f9801-158">The following steps create a package for the .NET Framework redistributable manually.</span></span> <span data-ttu-id="f9801-159">Das Paket enthält die angegebenen Parameter zum Installieren von .NET Framework und zu dem Speicherort, von dem das Paket an die Zielcomputer verteilt wird.</span><span class="sxs-lookup"><span data-stu-id="f9801-159">The package contains the specified parameters for installing the .NET Framework and the location from where the package will be distributed to the target computers.</span></span>

<span data-ttu-id="f9801-160">So erstellen Sie ein Paket</span><span class="sxs-lookup"><span data-stu-id="f9801-160">To create a package:</span></span>

1. <span data-ttu-id="f9801-161">Wählen Sie in der Configuration Manager-Konsole **Softwarebibliothek** aus.</span><span class="sxs-lookup"><span data-stu-id="f9801-161">In the Configuration Manager console, choose **Software Library**.</span></span>

2. <span data-ttu-id="f9801-162">Erweitern Sie im Arbeitsbereich **Softwarebibliothek** den Knoten **Anwendungsverwaltung**, und wählen Sie dann **Pakete** aus.</span><span class="sxs-lookup"><span data-stu-id="f9801-162">In the **Software Library** workspace, expand **Application Management**, and then choose **Packages**.</span></span>

3. <span data-ttu-id="f9801-163">Wählen Sie auf der Registerkarte **Startseite** in der Gruppe **Erstellen** die Option **Paket erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="f9801-163">On the **Home** tab, in the **Create** group, choose **Create Package**.</span></span>

4. <span data-ttu-id="f9801-164">Geben Sie auf der Seite **Paket** im **Assistent zum Erstellen von Paketen und Programmen** die folgenden Informationen ein:</span><span class="sxs-lookup"><span data-stu-id="f9801-164">On the **Package** page of the **Create Package and Program Wizard**, enter the following information:</span></span>

    - <span data-ttu-id="f9801-165">Name: `.NET Framework 4.5`</span><span class="sxs-lookup"><span data-stu-id="f9801-165">Name: `.NET Framework 4.5`</span></span>

    - <span data-ttu-id="f9801-166">Hersteller: `Microsoft`</span><span class="sxs-lookup"><span data-stu-id="f9801-166">Manufacturer: `Microsoft`</span></span>

    - <span data-ttu-id="f9801-167">Sprache:</span><span class="sxs-lookup"><span data-stu-id="f9801-167">Language.</span></span> `English (US)`

5. <span data-ttu-id="f9801-168">Wählen Sie **Dieses Paket enthält Quelldateien** aus, und wählen Sie anschließend **Durchsuchen** aus, um den lokalen oder Netzwerkordner mit den .NET Framework-Installationsdateien auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="f9801-168">Choose **This package contains source files**, and then choose **Browse** to select the local or network folder that contains the .NET Framework installation files.</span></span> <span data-ttu-id="f9801-169">Wenn Sie den Ordner ausgewählt haben, wählen Sie **OK** und anschließend **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="f9801-169">When you have selected the folder, choose **OK**, and then choose **Next**.</span></span>

6. <span data-ttu-id="f9801-170">Wählen Sie auf der Seite **Programmtyp** des Assistenten **Standardprogramm** und anschließend **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="f9801-170">On the **Program Type** page of the wizard, choose **Standard Program**, and then choose **Next**.</span></span>

7. <span data-ttu-id="f9801-171">Geben Sie auf der Seite **Programm** im **Assistent zum Erstellen von Paketen und Programmen** die folgenden Informationen ein:</span><span class="sxs-lookup"><span data-stu-id="f9801-171">On the **Program** page of the **Create Package and Program Wizard**, enter the following information:</span></span>

    1. <span data-ttu-id="f9801-172">**Name:** `.NET Framework 4.5`</span><span class="sxs-lookup"><span data-stu-id="f9801-172">**Name:** `.NET Framework 4.5`</span></span>

    2. <span data-ttu-id="f9801-173">**Befehlszeile:** `dotNetFx45_Full_x86_x64.exe /q /norestart /ChainingPackage ADMINDEPLOYMENT` (Befehlszeilenoptionen werden in der Tabelle weiter unten beschrieben)</span><span class="sxs-lookup"><span data-stu-id="f9801-173">**Command line:** `dotNetFx45_Full_x86_x64.exe /q /norestart /ChainingPackage ADMINDEPLOYMENT` (command-line options are described in the table after these steps)</span></span>

    3. <span data-ttu-id="f9801-174">**Ausführen:** Wählen Sie **Ausgeblendet** aus.</span><span class="sxs-lookup"><span data-stu-id="f9801-174">**Run:** Choose **Hidden**.</span></span>

    4. <span data-ttu-id="f9801-175">**Programmausführung:** Wählen Sie die Option aus, die angibt, dass das Programm unabhängig davon, ob ein Benutzer angemeldet ist, ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="f9801-175">**Program can run:** Choose the option that specifies that the program can run regardless of whether a user is logged on.</span></span>

8. <span data-ttu-id="f9801-176">Wählen Sie auf der Seite **Anforderungen** zum Übernehmen der Standardwerte **Weiter** aus, und schließen Sie dann den Assistenten ab.</span><span class="sxs-lookup"><span data-stu-id="f9801-176">On the **Requirements** page, choose **Next** to accept the default values, and then complete the wizard.</span></span>

<span data-ttu-id="f9801-177">In der folgenden Tabelle werden die in Schritt 7 angegebenen Befehlszeilenoptionen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f9801-177">The following table describes the command-line options specified in step 7.</span></span>

|<span data-ttu-id="f9801-178">Option</span><span class="sxs-lookup"><span data-stu-id="f9801-178">Option</span></span>|<span data-ttu-id="f9801-179">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f9801-179">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="f9801-180">**/q**</span><span class="sxs-lookup"><span data-stu-id="f9801-180">**/q**</span></span>|<span data-ttu-id="f9801-181">Legt den stillen Modus fest.</span><span class="sxs-lookup"><span data-stu-id="f9801-181">Sets quiet mode.</span></span> <span data-ttu-id="f9801-182">Es sind keine Benutzereingaben erforderlich, und es wird keine Ausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f9801-182">No user input is required, and no output is shown.</span></span>|
|<span data-ttu-id="f9801-183">**/norestart**</span><span class="sxs-lookup"><span data-stu-id="f9801-183">**/norestart**</span></span>|<span data-ttu-id="f9801-184">Verhindert, dass das Setupprogramm automatisch erneut gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="f9801-184">Prevents the Setup program from rebooting automatically.</span></span> <span data-ttu-id="f9801-185">Bei Verwendung dieser Option muss Configuration Manager den Neustart des Computers behandeln.</span><span class="sxs-lookup"><span data-stu-id="f9801-185">If you use this option, Configuration Manager must handle the computer restart.</span></span>|
|<span data-ttu-id="f9801-186">**/chainingpackage** *PackageName*</span><span class="sxs-lookup"><span data-stu-id="f9801-186">**/chainingpackage** *PackageName*</span></span>|<span data-ttu-id="f9801-187">Gibt den Namen des Pakets an, das das Verketten ausführt.</span><span class="sxs-lookup"><span data-stu-id="f9801-187">Specifies the name of the package that is doing the chaining.</span></span> <span data-ttu-id="f9801-188">Diese Informationen werden zusammen mit anderen Installationssitzungsinformationen für Personen ausgegeben, die sich beim Microsoft-Programm zur Verbesserung der Benutzerfreundlichkeit (Customer Experience Improvement Program, CEIP) registriert haben.</span><span class="sxs-lookup"><span data-stu-id="f9801-188">This information is reported with other installation session information for those who have signed up for the Microsoft Customer Experience Improvement Program (CEIP).</span></span> <span data-ttu-id="f9801-189">Wenn der Paketname Leerzeichen enthält, verwenden Sie als Trennzeichen doppelte Anführungszeichen, z.B. **/chainingpackage "Chaining Product"**.</span><span class="sxs-lookup"><span data-stu-id="f9801-189">If the package name includes spaces, use double quotation marks as delimiters; for example: **/chainingpackage "Chaining Product"**.</span></span>|

<span data-ttu-id="f9801-190">Mit diesen Schritten wird ein Paket namens ".NET Framework 4.5" erstellt.</span><span class="sxs-lookup"><span data-stu-id="f9801-190">These steps create a package named .NET Framework 4.5.</span></span> <span data-ttu-id="f9801-191">Das Programm stellt eine automatische Installation von .NET Framework 4.5 bereit.</span><span class="sxs-lookup"><span data-stu-id="f9801-191">The program deploys a silent installation of the .NET Framework 4.5.</span></span> <span data-ttu-id="f9801-192">In einer automatischen Installation greifen Benutzer nicht in den Installationsvorgang ein, und die Verkettungsanwendung muss den Rückgabecode erfassen und den Neustart initiieren. Weitere Informationen finden Sie in der unter [Getting Progress Information from an Installation Package (Abrufen von Statusinformationen aus einem Installationspaket)](https://docs.microsoft.com/previous-versions/cc825975(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="f9801-192">In a silent installation, users do not interact with the installation process, and the chaining application has to capture the return code and handle rebooting; see [Getting Progress Information from an Installation Package](https://docs.microsoft.com/previous-versions/cc825975(v=vs.100)).</span></span>

<a name="select_dist_point"></a>

### <a name="select-a-distribution-point"></a><span data-ttu-id="f9801-193">Auswählen eines Verteilungspunkts</span><span class="sxs-lookup"><span data-stu-id="f9801-193">Select a distribution point</span></span>

<span data-ttu-id="f9801-194">Um das Paket und Programm von einem Server an Clientcomputer zu verteilen, müssen Sie zuerst ein Standortsystem als Verteilungspunkt festlegen und das Paket dann an den Verteilungspunkt verteilen.</span><span class="sxs-lookup"><span data-stu-id="f9801-194">To distribute the package and program to client computers from a server, you must first designate a site system as a distribution point and then distribute the package to the distribution point.</span></span>

<span data-ttu-id="f9801-195">Führen Sie die folgenden Schritte aus, um einen Verteilungspunkt für das im vorherigen Abschnitt erstellte .NET Framework 4.5-Paket auszuwählen:</span><span class="sxs-lookup"><span data-stu-id="f9801-195">Use the following steps to select a distribution point for the .NET Framework 4.5 package you created in the previous section:</span></span>

1. <span data-ttu-id="f9801-196">Wählen Sie in der Configuration Manager-Konsole **Softwarebibliothek** aus.</span><span class="sxs-lookup"><span data-stu-id="f9801-196">In the Configuration Manager console, choose **Software Library**.</span></span>

2. <span data-ttu-id="f9801-197">Erweitern Sie im Arbeitsbereich **Softwarebibliothek** den Knoten **Anwendungsverwaltung**, und wählen Sie dann **Pakete** aus.</span><span class="sxs-lookup"><span data-stu-id="f9801-197">In the **Software Library** workspace, expand **Application Management**, and then choose **Packages**.</span></span>

3. <span data-ttu-id="f9801-198">Wählen Sie aus der Liste von Paketen das Paket **.NET Framework 4.5** aus, das Sie im vorherigen Abschnitt erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="f9801-198">From the list of packages, select the package **.NET Framework 4.5** that you created in the previous section.</span></span>

4. <span data-ttu-id="f9801-199">Wählen Sie auf der Registerkarte **Startseite** in der Gruppe **Bereitstellung** die Option **Inhalt verteilen** aus.</span><span class="sxs-lookup"><span data-stu-id="f9801-199">On the **Home** tab, in the **Deployment** group, choose **Distribute Content**.</span></span>

5. <span data-ttu-id="f9801-200">Wählen Sie auf der Registerkarte **Allgemein** im **Assistent für die Verteilung von Inhalt** die Option **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="f9801-200">On the **General** tab of the **Distribute Content Wizard**, choose **Next**.</span></span>

6. <span data-ttu-id="f9801-201">Wählen Sie auf der Seite **Inhaltsziel** des Assistenten **Hinzufügen** und anschließend **Verteilungspunkt** aus.</span><span class="sxs-lookup"><span data-stu-id="f9801-201">On the **Content Destination** page of the wizard, choose **Add**, and then choose **Distribution Point**.</span></span>

7. <span data-ttu-id="f9801-202">Wählen Sie im Dialogfeld **Verteilungspunkte hinzufügen** mindestens einen Verteilungspunkt aus, von dem das Paket und Programm gehostet werden sollen, und wählen Sie dann **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="f9801-202">In the **Add Distribution Points** dialog box, select the distribution point(s) that will host the package and program, and then choose **OK**.</span></span>

8. <span data-ttu-id="f9801-203">Durchlaufen Sie den Assistenten.</span><span class="sxs-lookup"><span data-stu-id="f9801-203">Complete the wizard.</span></span>

<span data-ttu-id="f9801-204">Das Paket enthält jetzt alle Informationen, die Sie für die automatische Bereitstellung von .NET Framework 4.5 benötigen.</span><span class="sxs-lookup"><span data-stu-id="f9801-204">The package now contains all the information you need to silently deploy the .NET Framework 4.5.</span></span> <span data-ttu-id="f9801-205">Überprüfen Sie vor dem Bereitstellen des Pakets und Programms, ob die Installation auf dem Verteilungspunkt ausgeführt wurde. Weitere Informationen finden Sie in der Configuration Manager-Dokumentationsbibliothek [Überwachen von mit System Center Configuration Manager verteilten Inhalten](https://docs.microsoft.com/sccm/core/servers/deploy/configure/monitor-content-you-have-distributed) im Abschnitt „Überwachen von Inhalten“.</span><span class="sxs-lookup"><span data-stu-id="f9801-205">Before you deploy the package and program, verify that it was installed on the distribution point; see the "Monitor Content" section of [Monitor content you have distributed with System Center Configuration Manager](https://docs.microsoft.com/sccm/core/servers/deploy/configure/monitor-content-you-have-distributed) in the Configuration Manager Documentation Library.</span></span>

<a name="deploying_package"></a>

### <a name="deploy-the-package"></a><span data-ttu-id="f9801-206">Bereitstellen des Pakets</span><span class="sxs-lookup"><span data-stu-id="f9801-206">Deploy the package</span></span>

<span data-ttu-id="f9801-207">So stellen Sie das .NET Framework 4.5-Paket und -Programm bereit</span><span class="sxs-lookup"><span data-stu-id="f9801-207">To deploy the .NET Framework 4.5 package and program:</span></span>

1. <span data-ttu-id="f9801-208">Wählen Sie in der Configuration Manager-Konsole **Softwarebibliothek** aus.</span><span class="sxs-lookup"><span data-stu-id="f9801-208">In the Configuration Manager console, choose **Software Library**.</span></span>

2. <span data-ttu-id="f9801-209">Erweitern Sie im Arbeitsbereich **Softwarebibliothek** den Knoten **Anwendungsverwaltung**, und wählen Sie dann **Pakete** aus.</span><span class="sxs-lookup"><span data-stu-id="f9801-209">In the **Software Library** workspace, expand **Application Management**, and then choose **Packages**.</span></span>

3. <span data-ttu-id="f9801-210">Wählen Sie aus der Liste von Paketen das Paket **.NET Framework 4.5** aus, das Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="f9801-210">From the list of packages, select the package you created named **.NET Framework 4.5**.</span></span>

4. <span data-ttu-id="f9801-211">Wählen Sie auf der Registerkarte **Startseite** in der Gruppe **Bereitstellung** die Option **Bereitstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="f9801-211">On the **Home** tab, in the **Deployment** group, choose **Deploy**.</span></span>

5. <span data-ttu-id="f9801-212">Wählen Sie auf der Seite **Allgemein** im **Assistent zum Bereitstellen von Software** die Option **Durchsuchen** und anschließend die Sammlung aus, die Sie zuvor erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="f9801-212">On the **General** page of the **Deploy Software Wizard**, choose **Browse**, and then select the collection that you created earlier.</span></span> <span data-ttu-id="f9801-213">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="f9801-213">Choose **Next**.</span></span>

6. <span data-ttu-id="f9801-214">Überprüfen Sie auf der Seite **Inhalt** des Assistenten, ob der Punkt, von dem Sie die Software verteilen möchten, angezeigt wird. Wählen Sie anschließend **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="f9801-214">On the **Content** page of the wizard, verify that the point from which you want to distribute the software is displayed, and then choose **Next**.</span></span>

7. <span data-ttu-id="f9801-215">Bestätigen Sie auf der Seite **Bereitstellungseinstellungen** des Assistenten, dass **Aktion** auf **Installieren** festgelegt ist und dass **Zweck** auf **Erforderlich** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="f9801-215">On the **Deployment Settings** page of the wizard, confirm that **Action** is set to **Install**, and **Purpose** is set to **Required**.</span></span> <span data-ttu-id="f9801-216">Dadurch wird sichergestellt, dass die Installation des Softwarepakets auf den Zielcomputern erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="f9801-216">This ensures that the software package will be a mandatory installation on the targeted computers.</span></span> <span data-ttu-id="f9801-217">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="f9801-217">Choose **Next**.</span></span>

8. <span data-ttu-id="f9801-218">Geben Sie auf der Seite **Zeitplanung** des Assistenten an, wann .NET Framework installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="f9801-218">On the **Scheduling** page of the wizard, specify when you want the .NET Framework to be installed.</span></span> <span data-ttu-id="f9801-219">Sie können **Neu** auswählen, um eine Installationszeit zuzuweisen, oder die Software anweisen, die Installation bei An- oder Abmeldung des Benutzers oder so schnell wie möglich durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="f9801-219">You can choose **New** to assign an installation time, or instruct the software to install when the user logs on or off, or as soon as possible.</span></span> <span data-ttu-id="f9801-220">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="f9801-220">Choose **Next**.</span></span>

9. <span data-ttu-id="f9801-221">Verwenden Sie auf der Seite **Benutzerfreundlichkeit** des Assistenten die Standardwerte, und wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="f9801-221">On the **User Experience** page of the wizard, use the default values and choose **Next**.</span></span>

    > [!WARNING]
    > <span data-ttu-id="f9801-222">Möglicherweise gelten in Ihrer Produktionsumgebung Richtlinien, die eine andere Auswahl für den Bereitstellungszeitplan erfordern.</span><span class="sxs-lookup"><span data-stu-id="f9801-222">Your production environment might have policies that require different selections for the deployment schedule.</span></span> <span data-ttu-id="f9801-223">Informationen zu diesen Optionen finden Sie unter [Eigenschaften von „Ankündigungsname“: Registerkarte „Zeitplan“](https://docs.microsoft.com/previous-versions/system-center/configuration-manager-2007/bb694016%28v=technet.10%29).</span><span class="sxs-lookup"><span data-stu-id="f9801-223">For information about these options, see [Advertisement Name Properties: Schedule Tab](https://docs.microsoft.com/previous-versions/system-center/configuration-manager-2007/bb694016%28v=technet.10%29).</span></span>

10. <span data-ttu-id="f9801-224">Verwenden Sie auf der Seite **Verteilungspunkte** des Assistenten die Standardwerte, und wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="f9801-224">On the **Distribution Points** page of the wizard, use the default values and choose **Next**.</span></span>

11. <span data-ttu-id="f9801-225">Durchlaufen Sie den Assistenten.</span><span class="sxs-lookup"><span data-stu-id="f9801-225">Complete the wizard.</span></span> <span data-ttu-id="f9801-226">Sie können den Status der Bereitstellung im Knoten **Bereitstellungen** des Arbeitsbereichs **Überwachung** überwachen.</span><span class="sxs-lookup"><span data-stu-id="f9801-226">You can monitor the progress of the deployment in the **Deployments** node of the **Monitoring** workspace.</span></span>

<span data-ttu-id="f9801-227">Das Paket wird nun in der als Ziel festgelegten Sammlung bereitgestellt, und die automatische Installation von .NET Framework 4.5 beginnt.</span><span class="sxs-lookup"><span data-stu-id="f9801-227">The package will now be deployed to the targeted collection and the silent installation of .NET Framework 4.5 will begin.</span></span> <span data-ttu-id="f9801-228">Informationen zu Fehlercodes für die .NET Framework 4.5-Installation finden Sie weiter unten in diesem Thema im Abschnitt [Rückgabecodes](#return_codes).</span><span class="sxs-lookup"><span data-stu-id="f9801-228">For information about .NET Framework 4.5 installation error codes, see the [Return Codes](#return_codes) section later in this topic.</span></span>

<a name="resources"></a>

## <a name="resources"></a><span data-ttu-id="f9801-229">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="f9801-229">Resources</span></span>

<span data-ttu-id="f9801-230">Weitere Informationen zur Infrastruktur zum Testen der Bereitstellung des weitervertreibbaren .NET Framework 4.5-Pakets finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="f9801-230">For more information about the infrastructure for testing the deployment of the .NET Framework 4.5 redistributable package, see the following resources.</span></span>

<span data-ttu-id="f9801-231">**Active Directory, DNS, DHCP:**</span><span class="sxs-lookup"><span data-stu-id="f9801-231">**Active Directory, DNS, DHCP:**</span></span>

- [<span data-ttu-id="f9801-232">Active Directory Domain Services</span><span class="sxs-lookup"><span data-stu-id="f9801-232">Active Directory Domain Services</span></span>](/windows/desktop/ad/active-directory-domain-services)

- [<span data-ttu-id="f9801-233">Domain Name System (DNS)</span><span class="sxs-lookup"><span data-stu-id="f9801-233">Domain Name System (DNS)</span></span>](/windows-server/networking/dns/dns-top)

- [<span data-ttu-id="f9801-234">Dynamic Host Configuration-Protokoll (DHCP)</span><span class="sxs-lookup"><span data-stu-id="f9801-234">Dynamic Host Configuration Protocol (DHCP)</span></span>](/windows-server/networking/technologies/dhcp/dhcp-top)

<span data-ttu-id="f9801-235">**SQL Server 2008:**</span><span class="sxs-lookup"><span data-stu-id="f9801-235">**SQL Server 2008:**</span></span>

- <span data-ttu-id="f9801-236">[Installieren von SQL Server 2008 (SQL Server-Video)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/dd299415(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="f9801-236">[Installing SQL Server 2008 (SQL Server Video)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/dd299415(v=sql.100))</span></span>

- [<span data-ttu-id="f9801-237">SQL Server 2008-Sicherheit: Übersicht für Datenbankadministratoren</span><span class="sxs-lookup"><span data-stu-id="f9801-237">SQL Server 2008 Security Overview for Database Administrators</span></span>](https://download.microsoft.com/download/a/c/d/acd8e043-d69b-4f09-bc9e-4168b65aaa71/SQL2008SecurityOverviewforAdmins.docx)

<span data-ttu-id="f9801-238">**System Center 2012 Configuration Manager (Verwaltungspunkt, Verteilungspunkt):**</span><span class="sxs-lookup"><span data-stu-id="f9801-238">**System Center 2012 Configuration Manager (Management Point, Distribution Point):**</span></span>

- [<span data-ttu-id="f9801-239">Standortverwaltung für System Center 2012 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f9801-239">Site Administration for System Center 2012 Configuration Manager</span></span>](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg681983%28v=technet.10%29)

- [<span data-ttu-id="f9801-240">Planen und Bereitstellen einzelner Standorte mit Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f9801-240">Configuration Manager Single Site Planning and Deployment</span></span>](https://docs.microsoft.com/previous-versions/system-center/configuration-manager-2007/bb680961%28v=technet.10%29)

<span data-ttu-id="f9801-241">**System Center 2012 Configuration Manager-Client für Windows-Computer:**</span><span class="sxs-lookup"><span data-stu-id="f9801-241">**System Center 2012 Configuration Manager client for Windows computers:**</span></span>

- [<span data-ttu-id="f9801-242">Bereitstellen von Clients für System Center 2012 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f9801-242">Deploying Clients for System Center 2012 Configuration Manager</span></span>](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699391%28v=technet.10%29)

<a name="troubleshooting"></a>

## <a name="troubleshooting"></a><span data-ttu-id="f9801-243">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="f9801-243">Troubleshooting</span></span>

### <a name="log-file-locations"></a><span data-ttu-id="f9801-244">Protokolldateispeicherorte</span><span class="sxs-lookup"><span data-stu-id="f9801-244">Log file locations</span></span>

<span data-ttu-id="f9801-245">Beim Setup von .NET Framework werden die folgenden Protokolldateien generiert:</span><span class="sxs-lookup"><span data-stu-id="f9801-245">The following log files are generated during .NET Framework setup:</span></span>

- <span data-ttu-id="f9801-246">%temp%\Microsoft .NET Framework *version*\*.txt</span><span class="sxs-lookup"><span data-stu-id="f9801-246">%temp%\Microsoft .NET Framework *version*\*.txt</span></span>
- <span data-ttu-id="f9801-247">%temp%\Microsoft .NET Framework *version*\*.html,</span><span class="sxs-lookup"><span data-stu-id="f9801-247">%temp%\Microsoft .NET Framework *version*\*.html</span></span>

<span data-ttu-id="f9801-248">wobei *version* der .NET Framework-Version entspricht, die Sie installieren, z.B. 4.5 oder 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="f9801-248">where *version* is the version of the .NET Framework that you're installing, such as 4.5 or 4.7.2.</span></span>

<span data-ttu-id="f9801-249">Sie können ebenso das Verzeichnis angeben, in das Protokolldateien geschrieben werden. Verwenden Sie hierzu die Befehlszeilenoption `/log` im Installationsbefehl von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f9801-249">You can also specify the directory to which log files are written by using the `/log` command-line option in the .NET Framework installation command.</span></span> <span data-ttu-id="f9801-250">Weitere Informationen finden Sie im [Leitfaden für die Bereitstellung von .NET Framework für Entwickler](deployment-guide-for-developers.md#command-line-options).</span><span class="sxs-lookup"><span data-stu-id="f9801-250">For more information, see [.NET Framework deployment guide for developers](deployment-guide-for-developers.md#command-line-options).</span></span>

<span data-ttu-id="f9801-251">Mit dem [Protokollerfassungstool (Log Collection Tool)](https://www.microsoft.com/download/details.aspx?id=12493) können Sie die .NET Framework-Protokolldateien erfassen und eine komprimierte CAB-Datei erstellen, um die Größe der Dateien zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="f9801-251">You can use the [log collection tool](https://www.microsoft.com/download/details.aspx?id=12493) to collect the .NET Framework log files and to create a compressed cabinet (.cab) file that reduces the size of the files.</span></span>

<a name="return_codes"></a>

### <a name="return-codes"></a><span data-ttu-id="f9801-252">Rückgabecodes</span><span class="sxs-lookup"><span data-stu-id="f9801-252">Return codes</span></span>

<span data-ttu-id="f9801-253">Die folgende Tabelle enthält die gängigsten Rückgabecodes des weitervertreibbaren .NET Framework 4.5-Installationsprogramms.</span><span class="sxs-lookup"><span data-stu-id="f9801-253">The following table lists the most common return codes from the .NET Framework 4.5 redistributable installation program.</span></span> <span data-ttu-id="f9801-254">Die Rückgabecodes sind für alle Versionen des Installationsprogramms identisch.</span><span class="sxs-lookup"><span data-stu-id="f9801-254">The return codes are the same for all versions of the installer.</span></span>

<span data-ttu-id="f9801-255">Links zu ausführlichen Informationen finden Sie im nächsten Abschnitt [Downloadfehlercodes](#additional_error_codes).</span><span class="sxs-lookup"><span data-stu-id="f9801-255">For links to detailed information, see the next section, [Download error codes](#additional_error_codes).</span></span>

|<span data-ttu-id="f9801-256">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="f9801-256">Return code</span></span>|<span data-ttu-id="f9801-257">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f9801-257">Description</span></span>|
|-----------------|-----------------|
|<span data-ttu-id="f9801-258">0</span><span class="sxs-lookup"><span data-stu-id="f9801-258">0</span></span>|<span data-ttu-id="f9801-259">Die Installation wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="f9801-259">Installation completed successfully.</span></span>|
|<span data-ttu-id="f9801-260">1602</span><span class="sxs-lookup"><span data-stu-id="f9801-260">1602</span></span>|<span data-ttu-id="f9801-261">Der Benutzer hat die Installation abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="f9801-261">The user canceled installation.</span></span>|
|<span data-ttu-id="f9801-262">1603</span><span class="sxs-lookup"><span data-stu-id="f9801-262">1603</span></span>|<span data-ttu-id="f9801-263">Während der Installation ist ein schwerwiegender Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="f9801-263">A fatal error occurred during installation.</span></span>|
|<span data-ttu-id="f9801-264">1641</span><span class="sxs-lookup"><span data-stu-id="f9801-264">1641</span></span>|<span data-ttu-id="f9801-265">Ein Neustart ist erforderlich, um die Installation abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="f9801-265">A restart is required to complete the installation.</span></span> <span data-ttu-id="f9801-266">Diese Meldung zeigt eine erfolgreiche Installation an.</span><span class="sxs-lookup"><span data-stu-id="f9801-266">This message indicates success.</span></span>|
|<span data-ttu-id="f9801-267">3010</span><span class="sxs-lookup"><span data-stu-id="f9801-267">3010</span></span>|<span data-ttu-id="f9801-268">Ein Neustart ist erforderlich, um die Installation abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="f9801-268">A restart is required to complete the installation.</span></span> <span data-ttu-id="f9801-269">Diese Meldung zeigt eine erfolgreiche Installation an.</span><span class="sxs-lookup"><span data-stu-id="f9801-269">This message indicates success.</span></span>|
|<span data-ttu-id="f9801-270">5100</span><span class="sxs-lookup"><span data-stu-id="f9801-270">5100</span></span>|<span data-ttu-id="f9801-271">Der Computer des Benutzers erfüllt die Systemanforderungen nicht.</span><span class="sxs-lookup"><span data-stu-id="f9801-271">The user's computer does not meet system requirements.</span></span>|

<a name="additional_error_codes"></a>

### <a name="download-error-codes"></a><span data-ttu-id="f9801-272">Downloadfehlercodes</span><span class="sxs-lookup"><span data-stu-id="f9801-272">Download error codes</span></span>

- [<span data-ttu-id="f9801-273">Fehlercodes für BITS (Background Intelligent Transfer Service)</span><span class="sxs-lookup"><span data-stu-id="f9801-273">Background Intelligent Transfer Service (BITS) error codes</span></span>](/windows/desktop/Bits/bits-return-values)

- [<span data-ttu-id="f9801-274">Fehlercodes für URL-Moniker</span><span class="sxs-lookup"><span data-stu-id="f9801-274">URL moniker error codes</span></span>](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms775145%28v=vs.85%29)

- [<span data-ttu-id="f9801-275">Fehlercodes für WinHttp</span><span class="sxs-lookup"><span data-stu-id="f9801-275">WinHttp error codes</span></span>](/windows/desktop/WinHttp/error-messages)

<span data-ttu-id="f9801-276">Sonstige Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="f9801-276">Other error codes:</span></span>

- [<span data-ttu-id="f9801-277">Fehlercodes für Windows Installer</span><span class="sxs-lookup"><span data-stu-id="f9801-277">Windows Installer error codes</span></span>](/windows/desktop/msi/error-codes)

- <span data-ttu-id="f9801-278">[Ergebniscodes für Windows Update Agent](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc720442(v=ws.10))</span><span class="sxs-lookup"><span data-stu-id="f9801-278">[Windows Update Agent result codes](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc720442(v=ws.10))</span></span>

## <a name="see-also"></a><span data-ttu-id="f9801-279">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9801-279">See also</span></span>

- [<span data-ttu-id="f9801-280">Bereitstellungshandbuch für Entwickler</span><span class="sxs-lookup"><span data-stu-id="f9801-280">Deployment Guide for Developers</span></span>](deployment-guide-for-developers.md)
- [<span data-ttu-id="f9801-281">Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="f9801-281">System Requirements</span></span>](../get-started/system-requirements.md)
