---
title: 'Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-In'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 582eaef518e10acb4c4c356226ce0be24d1b4c35
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a><span data-ttu-id="59227-102">Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-In</span><span class="sxs-lookup"><span data-stu-id="59227-102">How to: View Certificates with the MMC Snap-in</span></span>
<span data-ttu-id="59227-103">Ein allgemeiner Typ der Anmeldeinformationen ist das X.509-Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="59227-103">A common type of credential is the X.509 certificate.</span></span> <span data-ttu-id="59227-104">Bei der Erstellung sicherer Dienste oder Clients können Sie ein Zertifikat angeben, das als Anmeldeinformation für Client oder Dienst über die Methoden wie beispielsweise <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="59227-104">When creating secure services or clients, you can specify a certificate be used as the client or service credential by using methods such as the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> method.</span></span> <span data-ttu-id="59227-105">Die Methode erfordert diverse Parameter; beispielsweise den Speicherplatz des Zertifikats und eines Werts, der für die Suche eines Zertifikats verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="59227-105">The method requires various parameters, such as the store where the certificate is stored and a value to use when searching for the certificate.</span></span> <span data-ttu-id="59227-106">Die folgende Prozedur veranschaulicht, wie die Speicherplätze auf einem Computer untersucht werden, um ein entsprechendes Zertifikat zu suchen.</span><span class="sxs-lookup"><span data-stu-id="59227-106">The following procedure demonstrates how to examine the stores on a computer to find an appropriate certificate.</span></span> <span data-ttu-id="59227-107">Ein Beispiel für den Fingerabdruck des Zertifikats suchen, finden Sie unter [wie: Abrufen des Fingerabdrucks eines Zertifikats](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="59227-107">For an example of finding the certificate thumbprint, see [How to: Retrieve the Thumbprint of a Certificate](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
### <a name="to-view-certificates-in-the-mmc-snap-in"></a><span data-ttu-id="59227-108">So zeigen Sie Zertifikate im MMC-Snap-In an</span><span class="sxs-lookup"><span data-stu-id="59227-108">To view certificates in the MMC snap-in</span></span>  
  
1.  <span data-ttu-id="59227-109">Öffnen Sie ein Eingabeaufforderungsfenster.</span><span class="sxs-lookup"><span data-stu-id="59227-109">Open a Command Prompt window.</span></span>  
  
2.  <span data-ttu-id="59227-110">Typ `mmc` , und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="59227-110">Type `mmc` and press the ENTER key.</span></span> <span data-ttu-id="59227-111">Beachten Sie, dass Sie in der Administratorrolle sein müssen, um Zertifikate im lokalen Computerspeicher anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="59227-111">Note that to view certificates in the local machine store, you must be in the Administrator role.</span></span>  
  
3.  <span data-ttu-id="59227-112">Auf der **Datei** Menü klicken Sie auf **Snap-In hinzufügen/entfernen**.</span><span class="sxs-lookup"><span data-stu-id="59227-112">On the **File** menu, click **Add/Remove Snap In**.</span></span>  
  
4.  <span data-ttu-id="59227-113">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="59227-113">Click **Add**.</span></span>  
  
5.  <span data-ttu-id="59227-114">In der **Standalone-Snap-in hinzufügen** wählen Sie im Dialogfeld **Zertifikate**.</span><span class="sxs-lookup"><span data-stu-id="59227-114">In the **Add Standalone Snap-in** dialog box, select **Certificates**.</span></span>  
  
6.  <span data-ttu-id="59227-115">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="59227-115">Click **Add**.</span></span>  
  
7.  <span data-ttu-id="59227-116">In der **Zertifikat-Snap-in** wählen Sie im Dialogfeld **Computerkonto** , und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="59227-116">In the **Certificates snap-in** dialog box, select **Computer account** and click **Next**.</span></span> <span data-ttu-id="59227-117">Sie können wahlweise **eigenes Benutzerkonto** oder **-Dienstkonto**.</span><span class="sxs-lookup"><span data-stu-id="59227-117">Optionally, you can select **My User account** or **Service account**.</span></span> <span data-ttu-id="59227-118">Sind Sie kein Verwalter des Computers, können Sie Zertifikate nur für Ihr Benutzerkonto verwalten.</span><span class="sxs-lookup"><span data-stu-id="59227-118">If you are not an administrator of the computer, you can manage certificates only for your user account.</span></span>  
  
8.  <span data-ttu-id="59227-119">In der **Computer auswählen** (Dialogfeld), klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="59227-119">In the **Select Computer** dialog box, click **Finish**.</span></span>  
  
9. <span data-ttu-id="59227-120">In der **Standalone-Snap-in hinzufügen** (Dialogfeld), klicken Sie auf **schließen**.</span><span class="sxs-lookup"><span data-stu-id="59227-120">In the **Add Standalone Snap-in** dialog box, click **Close**.</span></span>  
  
10. <span data-ttu-id="59227-121">Auf der **Snap-In hinzufügen/entfernen** (Dialogfeld), klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="59227-121">On the **Add/Remove Snap-in** dialog box, click **OK**.</span></span>  
  
11. <span data-ttu-id="59227-122">In der **Konsolenstamm** Fenster, klicken Sie auf **Zertifikate (lokaler Computer)** um das Zertifikat anzuzeigen, die für den Computer werden gespeichert.</span><span class="sxs-lookup"><span data-stu-id="59227-122">In the **Console Root** window, click **Certificates (Local Computer)** to view the certificate stores for the computer.</span></span>  
  
12. <span data-ttu-id="59227-123">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="59227-123">Optional.</span></span> <span data-ttu-id="59227-124">Wiederholen Sie die Schritte 3 bis 6, um Zertifikate für Ihr Konto anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="59227-124">To view certificates for your account, repeat steps 3 to 6.</span></span> <span data-ttu-id="59227-125">Klicken Sie in Schritt 7 anstelle **Computerkonto**, klicken Sie auf **eigenes Benutzerkonto** , und wiederholen Sie die Schritte 8 bis 10.</span><span class="sxs-lookup"><span data-stu-id="59227-125">In step 7, instead of selecting **Computer account**, click **My User account** and repeat steps 8 to 10.</span></span>  
  
13. <span data-ttu-id="59227-126">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="59227-126">Optional.</span></span> <span data-ttu-id="59227-127">Auf der **Datei** Menü klicken Sie auf **speichern** oder **speichern unter**.</span><span class="sxs-lookup"><span data-stu-id="59227-127">On the **File** menu, click **Save** or **Save As**.</span></span> <span data-ttu-id="59227-128">Speichern Sie die Konsolendatei zur späteren Wiederverwendung.</span><span class="sxs-lookup"><span data-stu-id="59227-128">Save the console file for later reuse.</span></span>  
  
## <a name="viewing-certificates-with-internet-explorer"></a><span data-ttu-id="59227-129">Anzeigen von Zertifikaten mit Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="59227-129">Viewing Certificates with Internet Explorer</span></span>  
 <span data-ttu-id="59227-130">Darüber hinaus können Sie Zertifikate mit dem Internet Explorer ansehen, exportieren, importieren und löschen.</span><span class="sxs-lookup"><span data-stu-id="59227-130">You can also view, export, import, and delete certificates by using Internet Explorer.</span></span>  
  
#### <a name="to-view-certificates-with-internet-explorer"></a><span data-ttu-id="59227-131">So zeigen Sie Zertifikate mit dem Internet Explorer an</span><span class="sxs-lookup"><span data-stu-id="59227-131">To view certificates with Internet Explorer</span></span>  
  
1.  <span data-ttu-id="59227-132">Klicken Sie in Internet Explorer auf **Tools**, klicken Sie dann auf **Internetoptionen** zum Anzeigen der **Internetoptionen** (Dialogfeld).</span><span class="sxs-lookup"><span data-stu-id="59227-132">In Internet Explorer, click **Tools**, then click **Internet Options** to display the **Internet Options** dialog box.</span></span>  
  
2.  <span data-ttu-id="59227-133">Klicken Sie auf die **Content** Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="59227-133">Click the **Content** tab.</span></span>  
  
3.  <span data-ttu-id="59227-134">Klicken Sie unter **Zertifikate**, klicken Sie auf **Zertifikate**.</span><span class="sxs-lookup"><span data-stu-id="59227-134">Under **Certificates**, click **Certificates**.</span></span>  
  
4.  <span data-ttu-id="59227-135">Zum Anzeigen von Details eines Zertifikats, wählen Sie das Zertifikat aus, und klicken Sie auf **Ansicht**.</span><span class="sxs-lookup"><span data-stu-id="59227-135">To view details of any certificate, select the certificate and click **View**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59227-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="59227-136">See Also</span></span>  
 [<span data-ttu-id="59227-137">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="59227-137">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="59227-138">Vorgehensweise: Erstellen von temporären Zertifikaten für die Verwendung während der Entwicklung</span><span class="sxs-lookup"><span data-stu-id="59227-138">How to: Create Temporary Certificates for Use During Development</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)  
 [<span data-ttu-id="59227-139">Vorgehensweise: Abrufen des Fingerabdrucks eines Zertifikats</span><span class="sxs-lookup"><span data-stu-id="59227-139">How to: Retrieve the Thumbprint of a Certificate</span></span>](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)
