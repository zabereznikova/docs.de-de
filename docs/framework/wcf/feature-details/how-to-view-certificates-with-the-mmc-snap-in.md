---
title: 'Gewusst wie: Anzeigen von Zertifikaten mit dem MMC-Snap-In'
ms.date: 02/25/2019
helpviewer_keywords:
- certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
ms.openlocfilehash: 35048c24e838c513909fae8bedcba287001f5cef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184783"
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a><span data-ttu-id="dfcac-102">Gewusst wie: Anzeigen von Zertifikaten mit dem MMC-Snap-In</span><span class="sxs-lookup"><span data-stu-id="dfcac-102">How to: View certificates with the MMC snap-in</span></span>
<span data-ttu-id="dfcac-103">Wenn Sie einen sicheren Client oder Dienst erstellen, können Sie ein [Zertifikat](working-with-certificates.md) als Anmeldeinformationen verwenden.</span><span class="sxs-lookup"><span data-stu-id="dfcac-103">When you create a secure client or service, you can use a [certificate](working-with-certificates.md) as the credential.</span></span> <span data-ttu-id="dfcac-104">Ein üblicher Anmeldeinformationstyp ist z. B. das X.509-Zertifikat, das Sie mit der <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> Methode erstellen.</span><span class="sxs-lookup"><span data-stu-id="dfcac-104">For example, a common type of credential is the X.509 certificate, which you create with the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="dfcac-105">Es gibt drei verschiedene Arten von Zertifikatspeichern, die Sie mit der Microsoft Management Console (MMC) auf Windows-Systemen untersuchen können:</span><span class="sxs-lookup"><span data-stu-id="dfcac-105">There are three different types of certificate stores that you can examine with the Microsoft Management Console (MMC) on Windows systems:</span></span>

- <span data-ttu-id="dfcac-106">Lokaler Computer: Der Speicher ist lokal auf dem Gerät und global für alle Benutzer auf dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="dfcac-106">Local computer: The store is local to the device and global to all users on the device.</span></span>

- <span data-ttu-id="dfcac-107">Aktueller Benutzer: Der Speicher ist lokal für das aktuelle Benutzerkonto auf dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="dfcac-107">Current user: The store is local to the current user account on the device.</span></span>

- <span data-ttu-id="dfcac-108">Dienstkonto: Der Speicher ist für einen bestimmten Dienst auf dem Gerät lokal.</span><span class="sxs-lookup"><span data-stu-id="dfcac-108">Service account: The store is local to a particular service on the device.</span></span>

## <a name="view-certificates-in-the-mmc-snap-in"></a><span data-ttu-id="dfcac-109">Anzeigen von Zertifikaten im MMC-Snap-In</span><span class="sxs-lookup"><span data-stu-id="dfcac-109">View certificates in the MMC snap-in</span></span>

<span data-ttu-id="dfcac-110">Das folgende Verfahren veranschaulicht, wie Sie die Speicher auf Ihrem lokalen Gerät überprüfen, um ein geeignetes Zertifikat zu finden:</span><span class="sxs-lookup"><span data-stu-id="dfcac-110">The following procedure demonstrates how to examine the stores on your local device to find an appropriate certificate:</span></span>
  
1. <span data-ttu-id="dfcac-111">Wählen Sie **Ausführen** aus dem **Startmenü** aus, und geben Sie dann *mmc*ein.</span><span class="sxs-lookup"><span data-stu-id="dfcac-111">Select **Run** from the **Start** menu, and then enter *mmc*.</span></span>

    <span data-ttu-id="dfcac-112">Die MMC wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dfcac-112">The MMC appears.</span></span>
  
2. <span data-ttu-id="dfcac-113">Wählen Sie im Menü **Datei** die Option **Snap In hinzufügen/entfernen**aus.</span><span class="sxs-lookup"><span data-stu-id="dfcac-113">From the **File** menu, select **Add/Remove Snap In**.</span></span>

    <span data-ttu-id="dfcac-114">Das Fenster **Snap-Ins hinzufügen oder entfernen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dfcac-114">The **Add or Remove Snap-ins** window appears.</span></span>
  
3. <span data-ttu-id="dfcac-115">Wählen Sie in der Liste **Verfügbare Snap-Ins** **Zertifikate**aus, und wählen Sie dann **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="dfcac-115">From the **Available snap-ins** list, choose **Certificates**, then select **Add**.</span></span>  

    ![Hinzufügen eines Zertifikat-Snap-Ins](./media/mmc-add-certificate-snap-in.png)
  
4. <span data-ttu-id="dfcac-117">Wählen Sie im **Snap-In-Fenster Zertifikate** die Option **Computerkonto**aus, und wählen Sie dann **Weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="dfcac-117">In the **Certificates snap-in** window, select **Computer account**, and then select **Next**.</span></span>
  
    <span data-ttu-id="dfcac-118">Optional können Sie **Mein Benutzerkonto** für den aktuellen Benutzer oder **Dienstkonto** für einen bestimmten Dienst auswählen.</span><span class="sxs-lookup"><span data-stu-id="dfcac-118">Optionally, you can select **My user account** for the current user or **Service account** for a particular service.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dfcac-119">Wenn Sie kein Administrator für Ihr Gerät sind, können Sie Zertifikate nur für Ihr Benutzerkonto verwalten.</span><span class="sxs-lookup"><span data-stu-id="dfcac-119">If you're not an administrator for your device, you can manage certificates only for your user account.</span></span>
  
5. <span data-ttu-id="dfcac-120">Lassen Sie im Fenster **Computer auswählen** den **lokalen Computer** aus, und wählen Sie dann Fertig **stellen**aus.</span><span class="sxs-lookup"><span data-stu-id="dfcac-120">In the **Select Computer** window, leave **Local computer** selected, and then select **Finish**.</span></span>  
  
6. <span data-ttu-id="dfcac-121">Wählen Sie im Fenster **Snap-in hinzufügen oder entfernen** **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="dfcac-121">In the **Add or Remove Snap-in** window, select **OK**.</span></span>  
  
    ![Hinzufügen eines Zertifikat-Snap-Ins](./media/mmc-certificate-snap-in-selected.png)

7. <span data-ttu-id="dfcac-123">Optional: Wählen Sie im Menü **Datei** **speichern** oder **Speichern** unter aus, um die MMC-Konsolendatei für die spätere Verwendung zu speichern.</span><span class="sxs-lookup"><span data-stu-id="dfcac-123">Optional: From the **File** menu, select **Save** or **Save As** to save the MMC console file for later use.</span></span>  

8. <span data-ttu-id="dfcac-124">Um Ihre Zertifikate im MMC-Snap-In anzuzeigen, wählen Sie **Konsolenstamm** im linken Bereich aus, und erweitern Sie dann **Zertifikate (Lokaler Computer)**.</span><span class="sxs-lookup"><span data-stu-id="dfcac-124">To view your certificates in the MMC snap-in, select **Console Root** in the left pane, then expand **Certificates (Local Computer)**.</span></span>

    <span data-ttu-id="dfcac-125">Eine Liste der Verzeichnisse für jeden Zertifikatstyp wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dfcac-125">A list of directories for each type of certificate appears.</span></span> <span data-ttu-id="dfcac-126">In jedem Zertifikatverzeichnis können Sie seine Zertifikate anzeigen, exportieren, importieren und löschen.</span><span class="sxs-lookup"><span data-stu-id="dfcac-126">From each certificate directory, you can view, export, import, and delete its certificates.</span></span>

## <a name="view-certificates-with-the-certificate-manager-tool"></a><span data-ttu-id="dfcac-127">Anzeigen von Zertifikaten mit dem Zertifikats-Manager-Tool</span><span class="sxs-lookup"><span data-stu-id="dfcac-127">View certificates with the Certificate Manager tool</span></span>

<span data-ttu-id="dfcac-128">Sie können Zertifikate auch anzeigen, exportieren, importieren und löschen, indem Sie das Zertifikats-Manager-Tool verwenden.</span><span class="sxs-lookup"><span data-stu-id="dfcac-128">You can also view, export, import, and delete certificates by using the Certificate Manager tool.</span></span>

### <a name="to-view-certificates-for-the-local-device"></a><span data-ttu-id="dfcac-129">So zeigen Sie Zertifikate für das lokale Gerät an</span><span class="sxs-lookup"><span data-stu-id="dfcac-129">To view certificates for the local device</span></span>

1. <span data-ttu-id="dfcac-130">Wählen Sie **Ausführen** aus dem **Startmenü** aus, und geben Sie dann *certlm.msc ein.*</span><span class="sxs-lookup"><span data-stu-id="dfcac-130">Select **Run** from the **Start** menu, and then enter *certlm.msc*.</span></span>

    <span data-ttu-id="dfcac-131">Das Zertifikats-Manager-Tool für das lokale Gerät wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dfcac-131">The Certificate Manager tool for the local device appears.</span></span>
  
2. <span data-ttu-id="dfcac-132">Um Ihre Zertifikate anzuzeigen, erweitern Sie unter **Zertifikate - Lokaler Computer** im linken Bereich das Verzeichnis für den Zertifikatstyp, den Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="dfcac-132">To view your certificates, under **Certificates - Local Computer** in the left pane, expand the directory for the type of certificate you want to view.</span></span>

### <a name="to-view-certificates-for-the-current-user"></a><span data-ttu-id="dfcac-133">So zeigen Sie Zertifikate für den aktuellen Benutzer an</span><span class="sxs-lookup"><span data-stu-id="dfcac-133">To view certificates for the current user</span></span>

1. <span data-ttu-id="dfcac-134">Wählen Sie **Ausführen** aus dem **Startmenü** aus, und geben Sie dann *certmgr.msc ein.*</span><span class="sxs-lookup"><span data-stu-id="dfcac-134">Select **Run** from the **Start** menu, and then enter *certmgr.msc*.</span></span>

    <span data-ttu-id="dfcac-135">Das Zertifikats-Manager-Tool für den aktuellen Benutzer wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dfcac-135">The Certificate Manager tool for the current user appears.</span></span>
  
2. <span data-ttu-id="dfcac-136">Um Ihre Zertifikate anzuzeigen, erweitern Sie unter **Zertifikate - Aktueller Benutzer** im linken Bereich das Verzeichnis für den Zertifikatstyp, den Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="dfcac-136">To view your certificates, under **Certificates - Current User** in the left pane, expand the directory for the type of certificate you want to view.</span></span>

## <a name="see-also"></a><span data-ttu-id="dfcac-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dfcac-137">See also</span></span>

- [<span data-ttu-id="dfcac-138">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="dfcac-138">Working with certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="dfcac-139">Gewusst wie: Erstellen temporärer Zertifikate für die Verwendung während der Entwicklung</span><span class="sxs-lookup"><span data-stu-id="dfcac-139">How to: Create temporary certificates for use during development</span></span>](how-to-create-temporary-certificates-for-use-during-development.md)
- [<span data-ttu-id="dfcac-140">Gewusst wie: Abrufen des Fingerabdrucks eines Zertifikats</span><span class="sxs-lookup"><span data-stu-id="dfcac-140">How to: Retrieve the thumbprint of a certificate</span></span>](how-to-retrieve-the-thumbprint-of-a-certificate.md)
