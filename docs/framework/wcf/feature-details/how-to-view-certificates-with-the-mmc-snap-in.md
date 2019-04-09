---
title: 'Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-in'
ms.date: 02/25/2019
helpviewer_keywords:
- certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
ms.openlocfilehash: 69f79b64250ff46524e7b4720d13351774875a3f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59167504"
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a><span data-ttu-id="d56d5-102">Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-in</span><span class="sxs-lookup"><span data-stu-id="d56d5-102">How to: View certificates with the MMC snap-in</span></span>
<span data-ttu-id="d56d5-103">Wenn Sie einen sicheren Client oder Dienst erstellen, können Sie eine [Zertifikat](working-with-certificates.md) als die Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="d56d5-103">When you create a secure client or service, you can use a [certificate](working-with-certificates.md) as the credential.</span></span> <span data-ttu-id="d56d5-104">Ein allgemeiner Typ der Anmeldeinformationen ist z. B. das x. 509-Zertifikat, das Sie erstellen, mit der <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="d56d5-104">For example, a common type of credential is the X.509 certificate, which you create with the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> method.</span></span> 

<span data-ttu-id="d56d5-105">Es gibt drei verschiedene Typen von Zertifikatspeichern, die Sie, mit der Microsoft Management Console (MMC) auf Windows-Systemen untersuchen können:</span><span class="sxs-lookup"><span data-stu-id="d56d5-105">There are three different types of certificate stores that you can examine with the Microsoft Management Console (MMC) on Windows systems:</span></span>

- <span data-ttu-id="d56d5-106">Lokaler Computer: Der Speicher ist lokal auf dem Gerät und global für alle Benutzer auf dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="d56d5-106">Local computer: The store is local to the device and global to all users on the device.</span></span>

- <span data-ttu-id="d56d5-107">Aktueller Benutzer: Der Speicher ist für das aktuelle Benutzerkonto auf dem Gerät lokal.</span><span class="sxs-lookup"><span data-stu-id="d56d5-107">Current user: The store is local to the current user account on the device.</span></span>

- <span data-ttu-id="d56d5-108">Dienstkonto: Der Speicher ist für einen bestimmten Dienst auf dem Gerät lokal.</span><span class="sxs-lookup"><span data-stu-id="d56d5-108">Service account: The store is local to a particular service on the device.</span></span>

## <a name="view-certificates-in-the-mmc-snap-in"></a><span data-ttu-id="d56d5-109">Anzeigen von Zertifikaten im MMC-Snap-in</span><span class="sxs-lookup"><span data-stu-id="d56d5-109">View certificates in the MMC snap-in</span></span> 

<span data-ttu-id="d56d5-110">Das folgende Verfahren veranschaulicht, wie der Speicher auf dem lokalen Gerät finden Sie ein entsprechendes Zertifikat zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="d56d5-110">The following procedure demonstrates how to examine the stores on your local device to find an appropriate certificate:</span></span> 
  
1. <span data-ttu-id="d56d5-111">Wählen Sie **ausführen** aus der **starten** Menü, und geben Sie dann *Mmc*.</span><span class="sxs-lookup"><span data-stu-id="d56d5-111">Select **Run** from the **Start** menu, and then enter *mmc*.</span></span> 

    <span data-ttu-id="d56d5-112">Die MMC wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d56d5-112">The MMC appears.</span></span> 
  
2. <span data-ttu-id="d56d5-113">Von der **Datei** , wählen Sie im Menü **Snap-In hinzufügen/entfernen**.</span><span class="sxs-lookup"><span data-stu-id="d56d5-113">From the **File** menu, select **Add/Remove Snap In**.</span></span> 
    
    <span data-ttu-id="d56d5-114">Die **hinzufügen oder Entfernen von-Snap-ins** Fenster wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d56d5-114">The **Add or Remove Snap-ins** window appears.</span></span>
  
3. <span data-ttu-id="d56d5-115">Von der **Verfügbare Snap-Ins** wählen **Zertifikate**, und wählen Sie dann **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="d56d5-115">From the **Available snap-ins** list, choose **Certificates**, then select **Add**.</span></span>  

    ![Zertifikat-Snap-in hinzufügen](./media/mmc-add-certificate-snap-in.png)
  
4. <span data-ttu-id="d56d5-117">In der **Zertifikat-Snap-in** wählen Sie im Fenster **Computerkonto**, und wählen Sie dann **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d56d5-117">In the **Certificates snap-in** window, select **Computer account**, and then select **Next**.</span></span> 
  
    <span data-ttu-id="d56d5-118">Wählen Sie optional **mein Benutzerkonto** für den aktuellen Benutzer oder **-Dienstkonto** für einen bestimmten Dienst.</span><span class="sxs-lookup"><span data-stu-id="d56d5-118">Optionally, you can select **My user account** for the current user or **Service account** for a particular service.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="d56d5-119">Wenn Sie für Ihr Gerät kein Administrator sind, können Sie Zertifikate nur für Ihr Benutzerkonto verwalten.</span><span class="sxs-lookup"><span data-stu-id="d56d5-119">If you're not an administrator for your device, you can manage certificates only for your user account.</span></span>
  
5. <span data-ttu-id="d56d5-120">In der **Computer auswählen** Fenster verlassen **lokalen Computer** ausgewählt, und wählen Sie dann **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="d56d5-120">In the **Select Computer** window, leave **Local computer** selected, and then select **Finish**.</span></span>  
  
6. <span data-ttu-id="d56d5-121">In der **hinzufügen oder Entfernen von Snap-Ins** wählen Sie im Fenster **OK**.</span><span class="sxs-lookup"><span data-stu-id="d56d5-121">In the **Add or Remove Snap-in** window, select **OK**.</span></span>  
  
    ![Zertifikat-Snap-in hinzufügen](./media/mmc-certificate-snap-in-selected.png)

7. <span data-ttu-id="d56d5-123">Optional: Von der **Datei** , wählen Sie im Menü **speichern** oder **speichern** zum Speichern der Datei des MMC-Konsole für die spätere Verwendung.</span><span class="sxs-lookup"><span data-stu-id="d56d5-123">Optional: From the **File** menu, select **Save** or **Save As** to save the MMC console file for later use.</span></span>  

8. <span data-ttu-id="d56d5-124">Wählen Sie zum Anzeigen Ihrer Zertifikate im MMC-Snap-in **Konsolenstamm** im linken Bereich, und erweitern Sie dann **Zertifikate (lokaler Computer)**.</span><span class="sxs-lookup"><span data-stu-id="d56d5-124">To view your certificates in the MMC snap-in, select **Console Root** in the left pane, then expand **Certificates (Local Computer)**.</span></span>

    <span data-ttu-id="d56d5-125">Eine Liste der Verzeichnisse für jeden Typ von Zertifikat wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d56d5-125">A list of directories for each type of certificate appears.</span></span> <span data-ttu-id="d56d5-126">Jedes Verzeichnis Zertifikat können Sie anzeigen, exportieren, importieren und die Zertifikate zu löschen.</span><span class="sxs-lookup"><span data-stu-id="d56d5-126">From each certificate directory, you can view, export, import, and delete its certificates.</span></span>

## <a name="view-certificates-with-the-certificate-manager-tool"></a><span data-ttu-id="d56d5-127">Anzeigen von Zertifikaten mit dem Zertifikat-Manager-tool</span><span class="sxs-lookup"><span data-stu-id="d56d5-127">View certificates with the Certificate Manager tool</span></span>

<span data-ttu-id="d56d5-128">Sie können auch anzeigen, exportieren, importieren und Löschen von Zertifikaten mit dem Zertifikat-Manager-Tool.</span><span class="sxs-lookup"><span data-stu-id="d56d5-128">You can also view, export, import, and delete certificates by using the Certificate Manager tool.</span></span>

### <a name="to-view-certificates-for-the-local-device"></a><span data-ttu-id="d56d5-129">Zertifikate für das lokale Gerät angezeigt</span><span class="sxs-lookup"><span data-stu-id="d56d5-129">To view certificates for the local device</span></span>

1. <span data-ttu-id="d56d5-130">Wählen Sie **ausführen** aus der **starten** Menü, und geben Sie dann *"certlm.msc"*.</span><span class="sxs-lookup"><span data-stu-id="d56d5-130">Select **Run** from the **Start** menu, and then enter *certlm.msc*.</span></span> 

    <span data-ttu-id="d56d5-131">Das Zertifikat-Manager-Tool für das lokale Gerät angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d56d5-131">The Certificate Manager tool for the local device appears.</span></span> 
  
2. <span data-ttu-id="d56d5-132">Die Zertifikate, unter anzeigen **Zertifikate – lokaler Computer** im linken Bereich, erweitern Sie in das Verzeichnis für den Typ des Zertifikats, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="d56d5-132">To view your certificates, under **Certificates - Local Computer** in the left pane, expand the directory for the type of certificate you want to view.</span></span>

### <a name="to-view-certificates-for-the-current-user"></a><span data-ttu-id="d56d5-133">Zum Anzeigen der Zertifikate für den aktuellen Benutzer</span><span class="sxs-lookup"><span data-stu-id="d56d5-133">To view certificates for the current user</span></span>

1. <span data-ttu-id="d56d5-134">Wählen Sie **ausführen** aus der **starten** Menü, und geben Sie dann *"Certmgr.msc"*.</span><span class="sxs-lookup"><span data-stu-id="d56d5-134">Select **Run** from the **Start** menu, and then enter *certmgr.msc*.</span></span> 

    <span data-ttu-id="d56d5-135">Das Zertifikat-Manager-Tool für den aktuellen Benutzer angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d56d5-135">The Certificate Manager tool for the current user appears.</span></span> 
  
2. <span data-ttu-id="d56d5-136">Die Zertifikate, unter anzeigen **Zertifikate - Aktueller Benutzer** im linken Bereich, erweitern Sie in das Verzeichnis für den Typ des Zertifikats, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="d56d5-136">To view your certificates, under **Certificates - Current User** in the left pane, expand the directory for the type of certificate you want to view.</span></span>

## <a name="see-also"></a><span data-ttu-id="d56d5-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d56d5-137">See also</span></span>

- [<span data-ttu-id="d56d5-138">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="d56d5-138">Working with certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="d56d5-139">Vorgehensweise: Erstellen von temporären Zertifikaten für die Verwendung während der Entwicklung</span><span class="sxs-lookup"><span data-stu-id="d56d5-139">How to: Create temporary certificates for use during development</span></span>](how-to-create-temporary-certificates-for-use-during-development.md)
- [<span data-ttu-id="d56d5-140">Vorgehensweise: Abrufen des Fingerabdrucks eines Zertifikats</span><span class="sxs-lookup"><span data-stu-id="d56d5-140">How to: Retrieve the thumbprint of a certificate</span></span>](how-to-retrieve-the-thumbprint-of-a-certificate.md)
