---
title: Technologiebeispiel für die Generikaserialisierung in Webdiensten
ms.date: 03/30/2017
ms.assetid: cdc15ea4-f678-4729-8ebe-188ae720bef7
ms.openlocfilehash: b233ed4374231c7e7ff2b6617a63c4e4c94612c2
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47108935"
---
# <a name="web-services-generics-serialization-technology-sample"></a>Technologiebeispiel für die Generikaserialisierung in Webdiensten
[Beispiel herunterladen](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/GenericsSerialization.zip.exe)  
  
 In diesem Beispiel wird die Verwendung und Steuerung der Generikaserialisierung in ASP.NET-Webdiensten veranschaulicht.  
  
### <a name="to-build-the-sample-using-visual-studio"></a>So erstellen Sie das Beispiel mithilfe von Visual Studio  
  
1.  Öffnen Sie Visual Studio, und wählen Sie im Menü **Datei** die Option **Neue Website** aus.  
  
2.  Wählen Sie im Dialogfeld **Neue Website** im linken Bereich die gewünschte Programmiersprache und im rechten Bereich **ASP.NET Web Service** aus.  
  
3.  Klicken Sie auf **Durchsuchen**, und navigieren Sie zum Unterverzeichnis „\CS\GenericsService“.  
  
4.  Wählen Sie "Service.asmx" aus, um die Datei in Visual Studio zu öffnen.  
  
5.  Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.  
  
> [!NOTE]
>  Die ersten fünf Schritte in dieser Liste sind optional. Die .NET Framework-Laufzeit generiert bei der ersten Anforderung des Diensts automatisch den Webdienst.  
  
> [!NOTE]
>  Die folgenden Schritte sind erforderlich, um das Beispiel zu erstellen.  
  
1.  Öffnen Sie [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)], und navigieren Sie zum Unterverzeichnis \CS.  
  
2.  Klicken Sie mit der rechten Maustaste auf das Symbol für das Verzeichnis „GenericsService“, und wählen Sie **Freigabe und Sicherheit** aus.  
  
3.  Wählen Sie auf der Registerkarte **Webfreigabe** die Option **Diesen Ordner freigeben** aus.  
  
> [!IMPORTANT]
>  Merken Sie sich den Namen des virtuellen Verzeichnisses, das im Bereich **Aliase** aufgeführt wird. Sie brauchen ihn zum Ausführen des Beispiels.  
  
### <a name="to-build-the-sample-using-internet-information-services"></a>So erstellen Sie das Beispiel mit Internetinformationsdienste  
  
1.  Öffnen Sie das Verwaltungs-Snap-In von **Internetinformationsdienste**, und erweitern Sie **Websites**.  
  
2.  Klicken Sie mit der linken Maustaste auf **Standardwebsite**, und wählen Sie **Neu** und dann **Virtuelles Verzeichnis**, um den **Assistenten zum Erstellen eines virtuellen Verzeichnisses** zu erstellen.  
  
3.  Klicken Sie auf **Weiter**, geben Sie den öffentlichen Alias für das virtuelle Verzeichnis ein, und klicken Sie auf **Weiter**.  
  
4.  Geben Sie den Pfad zum Verzeichnis ein, in dem Sie das Beispiel gespeichert haben (normalerweise das Unterverzeichnis „\CS\GenericsService“), und klicken Sie auf **Weiter**. Klicken Sie auf **Weiter**, um den Assistenten zu beenden.  
  
> [!IMPORTANT]
>  Merken Sie sich den Namen des virtuellen Verzeichnisses, das im Bereich **Alias** aufgeführt wird. Sie brauchen ihn zum Ausführen des Beispiels.  
  
### <a name="to-run-the-sample"></a>So führen Sie das Beispiel aus  
  
1.  Öffnen Sie ein Browserfenster, und wählen Sie die Adressleiste aus.  
  
2.  Typ `http://localhost/[virtual directory]/Service.asmx`, wobei `[virtual directory]` stellt dar, das virtuelle Verzeichnis, das Sie beim Erstellen des Beispiels angelegt erstellt haben.  
  
## <a name="remarks"></a>Hinweise  
 Im Beispiel wird eine Standard-ASP.NET-Seite angezeigt, die Links zur Definition des Webdiensts enthält. Sie können den Quellcode für den Webdienst ändern und zusätzlich die Anzeige anpassen. Weitere Informationen finden Sie unter [Erstellen von XML-Webdienstclients](https://msdn.microsoft.com/library/c606f3cb-4111-45b4-ae42-9300420fa16c).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Collections.Generic>  
- <xref:System.Web.Services>  
- <xref:System.Xml.Serialization>  
- [Serialisierung](../../../docs/standard/serialization/index.md)  
- [Mit ASP.NET- und XML-Webdienstclients erstellte XML-Webdienste](https://msdn.microsoft.com/library/1e64af78-d705-4384-b08d-591a45f4379c)
