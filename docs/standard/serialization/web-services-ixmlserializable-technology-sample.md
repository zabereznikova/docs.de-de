---
title: Technologiebeispiel für "IXmlSerializable" in Webdiensten
ms.date: 03/30/2017
ms.assetid: 0202d3f1-a50b-427d-a5bb-79208b8f1c22
ms.openlocfilehash: eb117f720e7541ac6460b5adfd0eecc7901f4fdf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="web-services-ixmlserializable-technology-sample"></a><span data-ttu-id="b4034-102">Technologiebeispiel für "IXmlSerializable" in Webdiensten</span><span class="sxs-lookup"><span data-stu-id="b4034-102">Web Services IXmlSerializable Technology Sample</span></span>
[<span data-ttu-id="b4034-103">Beispiel herunterladen</span><span class="sxs-lookup"><span data-stu-id="b4034-103">Download Sample</span></span>](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/IXmlSerializable.zip.exe)  
  
 <span data-ttu-id="b4034-104">In diesem Beispiel wird die Verwendung von <xref:System.Xml.Serialization.IXmlSerializable> zur Steuerung der Serialisierung benutzerdefinierter Typen in ASP.NET-Webdiensten veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b4034-104">This sample shows how to use <xref:System.Xml.Serialization.IXmlSerializable> to control the serialization of custom types in ASP.NET Web Services.</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="b4034-105">So erstellen Sie das Beispiel mithilfe von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b4034-105">To build the sample using Visual Studio</span></span>  
  
1.  <span data-ttu-id="b4034-106">Öffnen Sie [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)], und wählen Sie im Menü **Datei** die Option **Neue Website** aus.</span><span class="sxs-lookup"><span data-stu-id="b4034-106">Open [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] and select **New Web Site** from the **File** menu.</span></span>  
  
2.  <span data-ttu-id="b4034-107">Wählen Sie im Dialogfeld **Neue Website** im linken Bereich die gewünschte Programmiersprache und im rechten Bereich **ASP.NET-Webdienst** aus.</span><span class="sxs-lookup"><span data-stu-id="b4034-107">In the left pane of the **New Web Site** dialog, select your desired programming language, then from the right pane, select **ASP.NET Web Service**.</span></span>  
  
3.  <span data-ttu-id="b4034-108">Geben Sie als Namen für den neuen Webdienst **IXmlSerializable** ein.</span><span class="sxs-lookup"><span data-stu-id="b4034-108">Type **IXmlSerializable** as the name of the new Web service.</span></span>  
  
4.  <span data-ttu-id="b4034-109">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Symbol für Service.asmx, und wählen Sie **Löschen** aus. Wiederholen Sie diesen Schritt für die CodeBehind-Datei Service.asmx.</span><span class="sxs-lookup"><span data-stu-id="b4034-109">In the Solution Explorer window, right-click the icon for Service.asmx and select **Delete**; repeat this step for the Service.asmx codebehind file.</span></span>  
  
5.  <span data-ttu-id="b4034-110">Klicken Sie mit der rechten Maustaste auf das Projektverzeichnis, und wählen Sie **Vorhandenes Element hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="b4034-110">Right-click the project directory and select **Add Existing Item**.</span></span> <span data-ttu-id="b4034-111">Navigieren Sie im Dialogfeld zu dem Unterverzeichnis Service des sprachspezifischen Verzeichnisses.</span><span class="sxs-lookup"><span data-stu-id="b4034-111">In the dialog, navigate to the Service subdirectory of the language-specific directory.</span></span>  
  
6.  <span data-ttu-id="b4034-112">Wählen Sie Service.asmx aus, und wiederholen Sie dann diesen Schritt für die CodeBehind-Datei Service.asmx.</span><span class="sxs-lookup"><span data-stu-id="b4034-112">Select Service.asmx, then repeat this step for the Service.asmx codebehind file.</span></span>  
  
7.  <span data-ttu-id="b4034-113">Öffnen Sie [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)], und navigieren Sie zu dem Verzeichnis, in dem das im oben genannten Schritt 3 erstellte Verzeichnis IXmlSerializable enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="b4034-113">Open [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] and navigate to the directory that contains IXmlSerializable directory that you created in step 3 above.</span></span>  
  
8.  <span data-ttu-id="b4034-114">Klicken Sie mit der rechten Maustaste auf das Symbol für das Verzeichnis IXmlSerializable, und wählen Sie **Freigabe und Sicherheit** aus.</span><span class="sxs-lookup"><span data-stu-id="b4034-114">Right-click the icon for the IXmlSerializable directory and select **Sharing and Security**.</span></span>  
  
9. <span data-ttu-id="b4034-115">Wählen Sie auf der Registerkarte Webfreigabe die Option **Diesen Ordner freigeben** aus, und bestätigen Sie die Standardeinstellungen, einschließlich des Namens IXmlSerializable.</span><span class="sxs-lookup"><span data-stu-id="b4034-115">In the Web Sharing tab, select **Share this Folder**, and confirm the default settings, including the name IXmlSerializable.</span></span>  
  
10. <span data-ttu-id="b4034-116">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4034-116">Click **OK**.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="b4034-117">So führen Sie das Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="b4034-117">To run the sample</span></span>  
  
1.  <span data-ttu-id="b4034-118">Öffnen Sie ein Browserfenster, und wählen Sie die Adressleiste aus.</span><span class="sxs-lookup"><span data-stu-id="b4034-118">Open a browser window and select its address bar.</span></span>  
  
2.  <span data-ttu-id="b4034-119">Typ **http://localhost/IXmlSerializable/Service.asmx**.</span><span class="sxs-lookup"><span data-stu-id="b4034-119">Type **http://localhost/IXmlSerializable/Service.asmx**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4034-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4034-120">See Also</span></span>  
 <xref:System.Xml.Serialization.IXmlSerializable>  
 <xref:System.Xml.Serialization>  
 <xref:System.Xml.XmlConvert>  
 <xref:System.Xml.XmlQualifiedName>  
 <xref:System.Xml.XmlReader>  
 <xref:System.Xml.Schema.XmlSchema>  
 <xref:System.Xml.Schema.XmlSchemaSet>  
 <xref:System.Xml.XmlUrlResolver>  
 <xref:System.Xml.XmlWriter>
