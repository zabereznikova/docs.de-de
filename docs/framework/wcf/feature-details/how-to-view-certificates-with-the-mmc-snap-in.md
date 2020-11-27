---
title: 'Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-in'
description: Ein sicherer WCF-Client oder-Dienst kann ein Zertifikat als Anmelde Informationen verwenden. Erfahren Sie mehr über die Typen von Zertifikat speichern, die Sie mithilfe des MMC-Plug-ins untersuchen können.
ms.date: 02/25/2019
helpviewer_keywords:
- certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
ms.openlocfilehash: 1f20384f16b3b5b898f926258d76a6a2773eaaa1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280623"
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a><span data-ttu-id="9fc32-104">Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-in</span><span class="sxs-lookup"><span data-stu-id="9fc32-104">How to: View certificates with the MMC snap-in</span></span>

<span data-ttu-id="9fc32-105">Wenn Sie einen sicheren Client oder Dienst erstellen, können Sie ein [Zertifikat](working-with-certificates.md) als Anmelde Informationen verwenden.</span><span class="sxs-lookup"><span data-stu-id="9fc32-105">When you create a secure client or service, you can use a [certificate](working-with-certificates.md) as the credential.</span></span> <span data-ttu-id="9fc32-106">Beispielsweise handelt es sich bei einem allgemeinen Anmelde Informationstyp um das X. 509-Zertifikat, das Sie mit der- <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> Methode erstellen.</span><span class="sxs-lookup"><span data-stu-id="9fc32-106">For example, a common type of credential is the X.509 certificate, which you create with the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="9fc32-107">Es gibt drei verschiedene Typen von Zertifikat speichern, die Sie mit der Microsoft Management Console (MMC) auf Windows-Systemen untersuchen können:</span><span class="sxs-lookup"><span data-stu-id="9fc32-107">There are three different types of certificate stores that you can examine with the Microsoft Management Console (MMC) on Windows systems:</span></span>

- <span data-ttu-id="9fc32-108">Lokaler Computer: der Speicher ist für das Gerät lokal und für alle Benutzer auf dem Gerät Global.</span><span class="sxs-lookup"><span data-stu-id="9fc32-108">Local computer: The store is local to the device and global to all users on the device.</span></span>

- <span data-ttu-id="9fc32-109">Aktueller Benutzer: der Speicher ist für das aktuelle Benutzerkonto auf dem Gerät lokal.</span><span class="sxs-lookup"><span data-stu-id="9fc32-109">Current user: The store is local to the current user account on the device.</span></span>

- <span data-ttu-id="9fc32-110">Dienst Konto: der Speicher ist für einen bestimmten Dienst auf dem Gerät lokal.</span><span class="sxs-lookup"><span data-stu-id="9fc32-110">Service account: The store is local to a particular service on the device.</span></span>

## <a name="view-certificates-in-the-mmc-snap-in"></a><span data-ttu-id="9fc32-111">Anzeigen von Zertifikaten im MMC-Snap-in</span><span class="sxs-lookup"><span data-stu-id="9fc32-111">View certificates in the MMC snap-in</span></span>

<span data-ttu-id="9fc32-112">Im folgenden Verfahren wird veranschaulicht, wie Sie die Speicher auf Ihrem lokalen Gerät untersuchen, um ein entsprechendes Zertifikat zu finden:</span><span class="sxs-lookup"><span data-stu-id="9fc32-112">The following procedure demonstrates how to examine the stores on your local device to find an appropriate certificate:</span></span>
  
1. <span data-ttu-id="9fc32-113">Wählen Sie im **Startmenü** die Option **Ausführen** aus, und geben Sie dann *MMC* ein.</span><span class="sxs-lookup"><span data-stu-id="9fc32-113">Select **Run** from the **Start** menu, and then enter *mmc*.</span></span>

    <span data-ttu-id="9fc32-114">Die MMC wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9fc32-114">The MMC appears.</span></span>
  
2. <span data-ttu-id="9fc32-115">Wählen Sie im Menü **Datei** die Option **Snap-in hinzufügen/entfernen** aus.</span><span class="sxs-lookup"><span data-stu-id="9fc32-115">From the **File** menu, select **Add/Remove Snap In**.</span></span>

    <span data-ttu-id="9fc32-116">Das Fenster **Snap-Ins hinzufügen bzw. entfernen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9fc32-116">The **Add or Remove Snap-ins** window appears.</span></span>
  
3. <span data-ttu-id="9fc32-117">Wählen Sie in der Liste **Verfügbare Snap-Ins** die Option **Zertifikate** und dann **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="9fc32-117">From the **Available snap-ins** list, choose **Certificates**, then select **Add**.</span></span>  

    ![Zertifikat-Snap-in hinzufügen](./media/mmc-add-certificate-snap-in.png)
  
4. <span data-ttu-id="9fc32-119">Wählen Sie im Fenster **Zertifikate-Snap-in** die Option **Computer Konto** aus, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="9fc32-119">In the **Certificates snap-in** window, select **Computer account**, and then select **Next**.</span></span>
  
    <span data-ttu-id="9fc32-120">Optional können Sie das **Benutzerkonto** für das aktuelle Benutzer-oder **Dienst Konto** für einen bestimmten Dienst auswählen.</span><span class="sxs-lookup"><span data-stu-id="9fc32-120">Optionally, you can select **My user account** for the current user or **Service account** for a particular service.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9fc32-121">Wenn Sie kein Administrator für Ihr Gerät sind, können Sie Zertifikate nur für Ihr Benutzerkonto verwalten.</span><span class="sxs-lookup"><span data-stu-id="9fc32-121">If you're not an administrator for your device, you can manage certificates only for your user account.</span></span>
  
5. <span data-ttu-id="9fc32-122">Lassen Sie im Fenster **Computer auswählen** die Option **lokaler Computer** ausgewählt, und klicken Sie dann auf **Fertig** stellen.</span><span class="sxs-lookup"><span data-stu-id="9fc32-122">In the **Select Computer** window, leave **Local computer** selected, and then select **Finish**.</span></span>  
  
6. <span data-ttu-id="9fc32-123">Wählen Sie im Fenster **Snap-in hinzufügen/entfernen** die Option **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="9fc32-123">In the **Add or Remove Snap-in** window, select **OK**.</span></span>  
  
    ![Zertifikat-Snap-in hinzufügen](./media/mmc-certificate-snap-in-selected.png)

7. <span data-ttu-id="9fc32-125">Optional: Wählen Sie im Menü **Datei** die Option **Speichern** oder **Speichern** unter, um die MMC-Konsolen Datei zur späteren Verwendung zu speichern.</span><span class="sxs-lookup"><span data-stu-id="9fc32-125">Optional: From the **File** menu, select **Save** or **Save As** to save the MMC console file for later use.</span></span>  

8. <span data-ttu-id="9fc32-126">Um Ihre Zertifikate im MMC-Snap-in anzuzeigen, klicken Sie im linken Bereich auf **Konsolen** Stamm und dann auf **Zertifikate (lokaler Computer)**.</span><span class="sxs-lookup"><span data-stu-id="9fc32-126">To view your certificates in the MMC snap-in, select **Console Root** in the left pane, then expand **Certificates (Local Computer)**.</span></span>

    <span data-ttu-id="9fc32-127">Eine Liste der Verzeichnisse für jeden Zertifikattyp wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9fc32-127">A list of directories for each type of certificate appears.</span></span> <span data-ttu-id="9fc32-128">Aus jedem Zertifikat Verzeichnis können Sie die Zertifikate anzeigen, exportieren, importieren und löschen.</span><span class="sxs-lookup"><span data-stu-id="9fc32-128">From each certificate directory, you can view, export, import, and delete its certificates.</span></span>

## <a name="view-certificates-with-the-certificate-manager-tool"></a><span data-ttu-id="9fc32-129">Anzeigen von Zertifikaten mit dem Zertifikat-Manager-Tool</span><span class="sxs-lookup"><span data-stu-id="9fc32-129">View certificates with the Certificate Manager tool</span></span>

<span data-ttu-id="9fc32-130">Mit dem Zertifikat-Manager-Tool können Sie Zertifikate auch anzeigen, exportieren, importieren und löschen.</span><span class="sxs-lookup"><span data-stu-id="9fc32-130">You can also view, export, import, and delete certificates by using the Certificate Manager tool.</span></span>

### <a name="to-view-certificates-for-the-local-device"></a><span data-ttu-id="9fc32-131">So zeigen Sie Zertifikate für das lokale Gerät an</span><span class="sxs-lookup"><span data-stu-id="9fc32-131">To view certificates for the local device</span></span>

1. <span data-ttu-id="9fc32-132">Wählen Sie im **Startmenü** die Option **Ausführen** aus, und geben Sie dann *certlm. msc* ein.</span><span class="sxs-lookup"><span data-stu-id="9fc32-132">Select **Run** from the **Start** menu, and then enter *certlm.msc*.</span></span>

    <span data-ttu-id="9fc32-133">Das Certificate Manager-Tool für das lokale Gerät wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9fc32-133">The Certificate Manager tool for the local device appears.</span></span>
  
2. <span data-ttu-id="9fc32-134">Um Ihre Zertifikate anzuzeigen, erweitern Sie im linken Bereich unter **Zertifikate-lokaler Computer** das Verzeichnis für den Typ des Zertifikats, das Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="9fc32-134">To view your certificates, under **Certificates - Local Computer** in the left pane, expand the directory for the type of certificate you want to view.</span></span>

### <a name="to-view-certificates-for-the-current-user"></a><span data-ttu-id="9fc32-135">So zeigen Sie Zertifikate für den aktuellen Benutzer an</span><span class="sxs-lookup"><span data-stu-id="9fc32-135">To view certificates for the current user</span></span>

1. <span data-ttu-id="9fc32-136">Wählen Sie im Menü **Start** den Befehl **Ausführen** aus, und geben Sie *certmgr.msc* ein.</span><span class="sxs-lookup"><span data-stu-id="9fc32-136">Select **Run** from the **Start** menu, and then enter *certmgr.msc*.</span></span>

    <span data-ttu-id="9fc32-137">Das Tool „Zertifikat-Manager“ für den aktuellen Benutzer wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9fc32-137">The Certificate Manager tool for the current user appears.</span></span>
  
2. <span data-ttu-id="9fc32-138">Um Ihre Zertifikate anzuzeigen, erweitern Sie im linken Bereich unter **Zertifikate-Aktueller Benutzer** das Verzeichnis für den Typ des Zertifikats, das Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="9fc32-138">To view your certificates, under **Certificates - Current User** in the left pane, expand the directory for the type of certificate you want to view.</span></span>

## <a name="see-also"></a><span data-ttu-id="9fc32-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9fc32-139">See also</span></span>

- [<span data-ttu-id="9fc32-140">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="9fc32-140">Working with certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="9fc32-141">Vorgehensweise: Erstellen von temporären Zertifikaten für die Verwendung während der Entwicklung</span><span class="sxs-lookup"><span data-stu-id="9fc32-141">How to: Create temporary certificates for use during development</span></span>](how-to-create-temporary-certificates-for-use-during-development.md)
- [<span data-ttu-id="9fc32-142">Vorgehensweise: Abrufen des Fingerabdrucks eines Zertifikats</span><span class="sxs-lookup"><span data-stu-id="9fc32-142">How to: Retrieve the thumbprint of a certificate</span></span>](how-to-retrieve-the-thumbprint-of-a-certificate.md)
