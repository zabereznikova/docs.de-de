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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: be0c76371bda9e91e0becf8a9e09beb44e44dd3c
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="web-services-ixmlserializable-technology-sample"></a>Technologiebeispiel für "IXmlSerializable" in Webdiensten
[Beispiel herunterladen](http://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/IXmlSerializable.zip.exe)  
  
 In diesem Beispiel wird die Verwendung von <xref:System.Xml.Serialization.IXmlSerializable> zur Steuerung der Serialisierung benutzerdefinierter Typen in ASP.NET-Webdiensten veranschaulicht.  
  
### <a name="to-build-the-sample-using-visual-studio"></a>So erstellen Sie das Beispiel mithilfe von Visual Studio  
  
1.  Öffnen Sie [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)], und wählen Sie im Menü **Datei** die Option **Neue Website** aus.  
  
2.  Wählen Sie im Dialogfeld **Neue Website** im linken Bereich die gewünschte Programmiersprache und im rechten Bereich **ASP.NET-Webdienst** aus.  
  
3.  Geben Sie als Namen für den neuen Webdienst **IXmlSerializable** ein.  
  
4.  Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Symbol für Service.asmx, und wählen Sie **Löschen** aus. Wiederholen Sie diesen Schritt für die CodeBehind-Datei Service.asmx.  
  
5.  Klicken Sie mit der rechten Maustaste auf das Projektverzeichnis, und wählen Sie **Vorhandenes Element hinzufügen** aus. Navigieren Sie im Dialogfeld zu dem Unterverzeichnis Service des sprachspezifischen Verzeichnisses.  
  
6.  Wählen Sie Service.asmx aus, und wiederholen Sie dann diesen Schritt für die CodeBehind-Datei Service.asmx.  
  
7.  Öffnen Sie [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)], und navigieren Sie zu dem Verzeichnis, in dem das im oben genannten Schritt 3 erstellte Verzeichnis IXmlSerializable enthalten ist.  
  
8.  Klicken Sie mit der rechten Maustaste auf das Symbol für das Verzeichnis IXmlSerializable, und wählen Sie **Freigabe und Sicherheit** aus.  
  
9. Wählen Sie auf der Registerkarte Webfreigabe die Option **Diesen Ordner freigeben** aus, und bestätigen Sie die Standardeinstellungen, einschließlich des Namens IXmlSerializable.  
  
10. Klicken Sie auf **OK**.  
  
### <a name="to-run-the-sample"></a>So führen Sie das Beispiel aus  
  
1.  Öffnen Sie ein Browserfenster, und wählen Sie die Adressleiste aus.  
  
2.  Geben Sie **http://localhost/IXmlSerializable/Service.asmx** ein.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Xml.Serialization.IXmlSerializable>  
 <xref:System.Xml.Serialization>  
 <xref:System.Xml.XmlConvert>  
 <xref:System.Xml.XmlQualifiedName>  
 <xref:System.Xml.XmlReader>  
 <xref:System.Xml.Schema.XmlSchema>  
 <xref:System.Xml.Schema.XmlSchemaSet>  
 <xref:System.Xml.XmlUrlResolver>  
 <xref:System.Xml.XmlWriter>
