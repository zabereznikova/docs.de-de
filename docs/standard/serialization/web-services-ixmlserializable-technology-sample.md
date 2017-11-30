---
title: "Technologiebeispiel für \"IXmlSerializable\" in Webdiensten"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0202d3f1-a50b-427d-a5bb-79208b8f1c22
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 72c7e9e1cbf47dd54726a16ddeb58a193d62dc31
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="web-services-ixmlserializable-technology-sample"></a><span data-ttu-id="36838-102">Technologiebeispiel für "IXmlSerializable" in Webdiensten</span><span class="sxs-lookup"><span data-stu-id="36838-102">Web Services IXmlSerializable Technology Sample</span></span>
[<span data-ttu-id="36838-103">Beispiel herunterladen</span><span class="sxs-lookup"><span data-stu-id="36838-103">Download Sample</span></span>](http://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/IXmlSerializable.zip.exe)  
  
 <span data-ttu-id="36838-104">In diesem Beispiel wird die Verwendung von <xref:System.Xml.Serialization.IXmlSerializable> zur Steuerung der Serialisierung benutzerdefinierter Typen in ASP.NET-Webdiensten veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="36838-104">This sample shows how to use <xref:System.Xml.Serialization.IXmlSerializable> to control the serialization of custom types in ASP.NET Web Services.</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="36838-105">So erstellen Sie das Beispiel mithilfe von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="36838-105">To build the sample using Visual Studio</span></span>  
  
1.  <span data-ttu-id="36838-106">Öffnen Sie [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)], und wählen Sie im Menü **Datei** die Option **Neue Website** aus.</span><span class="sxs-lookup"><span data-stu-id="36838-106">Open [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] and select **New Web Site** from the **File** menu.</span></span>  
  
2.  <span data-ttu-id="36838-107">Wählen Sie im Dialogfeld **Neue Website** im linken Bereich die gewünschte Programmiersprache und im rechten Bereich **ASP.NET-Webdienst** aus.</span><span class="sxs-lookup"><span data-stu-id="36838-107">In the left pane of the **New Web Site** dialog, select your desired programming language, then from the right pane, select **ASP.NET Web Service**.</span></span>  
  
3.  <span data-ttu-id="36838-108">Geben Sie als Namen für den neuen Webdienst **IXmlSerializable** ein.</span><span class="sxs-lookup"><span data-stu-id="36838-108">Type **IXmlSerializable** as the name of the new Web service.</span></span>  
  
4.  <span data-ttu-id="36838-109">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Symbol für Service.asmx, und wählen Sie **Löschen** aus. Wiederholen Sie diesen Schritt für die CodeBehind-Datei Service.asmx.</span><span class="sxs-lookup"><span data-stu-id="36838-109">In the Solution Explorer window, right-click the icon for Service.asmx and select **Delete**; repeat this step for the Service.asmx codebehind file.</span></span>  
  
5.  <span data-ttu-id="36838-110">Klicken Sie mit der rechten Maustaste auf das Projektverzeichnis, und wählen Sie **Vorhandenes Element hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="36838-110">Right-click the project directory and select **Add Existing Item**.</span></span> <span data-ttu-id="36838-111">Navigieren Sie im Dialogfeld zu dem Unterverzeichnis Service des sprachspezifischen Verzeichnisses.</span><span class="sxs-lookup"><span data-stu-id="36838-111">In the dialog, navigate to the Service subdirectory of the language-specific directory.</span></span>  
  
6.  <span data-ttu-id="36838-112">Wählen Sie Service.asmx aus, und wiederholen Sie dann diesen Schritt für die CodeBehind-Datei Service.asmx.</span><span class="sxs-lookup"><span data-stu-id="36838-112">Select Service.asmx, then repeat this step for the Service.asmx codebehind file.</span></span>  
  
7.  <span data-ttu-id="36838-113">Öffnen Sie [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)], und navigieren Sie zu dem Verzeichnis, in dem das im oben genannten Schritt 3 erstellte Verzeichnis IXmlSerializable enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="36838-113">Open [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] and navigate to the directory that contains IXmlSerializable directory that you created in step 3 above.</span></span>  
  
8.  <span data-ttu-id="36838-114">Klicken Sie mit der rechten Maustaste auf das Symbol für das Verzeichnis IXmlSerializable, und wählen Sie **Freigabe und Sicherheit** aus.</span><span class="sxs-lookup"><span data-stu-id="36838-114">Right-click the icon for the IXmlSerializable directory and select **Sharing and Security**.</span></span>  
  
9. <span data-ttu-id="36838-115">Wählen Sie auf der Registerkarte Webfreigabe die Option **Diesen Ordner freigeben** aus, und bestätigen Sie die Standardeinstellungen, einschließlich des Namens IXmlSerializable.</span><span class="sxs-lookup"><span data-stu-id="36838-115">In the Web Sharing tab, select **Share this Folder**, and confirm the default settings, including the name IXmlSerializable.</span></span>  
  
10. <span data-ttu-id="36838-116">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="36838-116">Click **OK**.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="36838-117">So führen Sie das Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="36838-117">To run the sample</span></span>  
  
1.  <span data-ttu-id="36838-118">Öffnen Sie ein Browserfenster, und wählen Sie die Adressleiste aus.</span><span class="sxs-lookup"><span data-stu-id="36838-118">Open a browser window and select its address bar.</span></span>  
  
2.  <span data-ttu-id="36838-119">Geben Sie **http://localhost/IXmlSerializable/Service.asmx** ein.</span><span class="sxs-lookup"><span data-stu-id="36838-119">Type **http://localhost/IXmlSerializable/Service.asmx**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36838-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36838-120">See Also</span></span>  
 <xref:System.Xml.Serialization.IXmlSerializable>  
 <xref:System.Xml.Serialization>  
 <xref:System.Xml.XmlConvert>  
 <xref:System.Xml.XmlQualifiedName>  
 <xref:System.Xml.XmlReader>  
 <xref:System.Xml.Schema.XmlSchema>  
 <xref:System.Xml.Schema.XmlSchemaSet>  
 <xref:System.Xml.XmlUrlResolver>  
 <xref:System.Xml.XmlWriter>
