---
title: 'Vorgehensweise: Erstellen eines grundlegenden Atom-Feeds'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6e0cacc1-9b11-4665-adb7-577a62626fd6
ms.openlocfilehash: 0317e7b42f589b31f5c77b89d26cb46815f13054
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599047"
---
# <a name="how-to-create-a-basic-atom-feed"></a>Vorgehensweise: Erstellen eines grundlegenden Atom-Feeds
Windows Communication Foundation (WCF) ermöglicht es Ihnen, einen Dienst zu erstellen, der einen Syndizierungs Feed verfügbar macht. In diesem Thema wird erläutert, wie ein Syndication-Dienst erstellt wird, der einen Atom-Syndication-Feed verfügbar macht.  
  
### <a name="to-create-a-basic-syndication-service"></a>So erstellen Sie einen grundlegenden Syndication-Dienst  
  
1. Definieren Sie einen Dienstvertrag mit einer Schnittstelle, die mit dem <xref:System.ServiceModel.Web.WebGetAttribute>-Attribut gekennzeichnet ist. Jeder Vorgang, der als Syndication-Feed verfügbar gemacht wird, sollte ein <xref:System.ServiceModel.Syndication.Atom10FeedFormatter>-Objekt zurückgeben.  
  
     [!code-csharp[htAtomBasic#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#0)]
     [!code-vb[htAtomBasic#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#0)]  
  
    > [!NOTE]
    > Alle Dienstvorgänge, auf die das <xref:System.ServiceModel.Web.WebGetAttribute>-Attribut angewendet wird, werden HTTP GET-Anforderungen zugeordnet. Wenn Sie den Vorgang einer anderen HTTP-Methode zuordnen möchten, verwenden Sie stattdessen <xref:System.ServiceModel.Web.WebInvokeAttribute>. Weitere Informationen finden Sie unter Gewusst [wie: Erstellen eines grundlegenden WCF-Web-HTTP-Diensts](how-to-create-a-basic-wcf-web-http-service.md).  
  
2. Implementieren Sie den Dienstvertrag.  
  
     [!code-csharp[htAtomBasic#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#1)]
     [!code-vb[htAtomBasic#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#1)]  
  
3. Erstellen Sie ein <xref:System.ServiceModel.Syndication.SyndicationFeed>-Objekt, und fügen Sie einen Autor, eine Kategorie und eine Beschreibung hinzu.  
  
     [!code-csharp[htAtomBasic#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#2)]
     [!code-vb[htAtomBasic#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#2)]  
  
4. Erstellen Sie mehrere <xref:System.ServiceModel.Syndication.SyndicationItem>-Objekte.  
  
     [!code-csharp[htAtomBasic#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#3)]
     [!code-vb[htAtomBasic#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#3)]  
  
5. Fügen Sie die <xref:System.ServiceModel.Syndication.SyndicationItem>-Objekte dem Feed hinzu.  
  
     [!code-csharp[htAtomBasic#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#4)]
     [!code-vb[htAtomBasic#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#4)]  
  
6. Geben Sie den Feed zurück.  
  
     [!code-csharp[htAtomBasic#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#5)]
     [!code-vb[htAtomBasic#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#5)]  
  
### <a name="to-host-the-service"></a>So hosten Sie den Dienst  
  
1. Erstellen eines <xref:System.ServiceModel.Web.WebServiceHost>-Objekts  
  
     [!code-csharp[htAtomBasic#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#6)]
     [!code-vb[htAtomBasic#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#6)]  
  
2. Öffnen Sie den Diensthost, laden Sie den Feed vom Dienst, zeigen Sie den Feed an, und warten Sie darauf, dass der Benutzer die Eingabetaste drückt.  
  
     [!code-csharp[htAtomBasic#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#8)]
     [!code-vb[htAtomBasic#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#8)]  
  
### <a name="to-call-getblog-with-an-http-get"></a>So rufen Sie GetBlog() mit HTTP GET auf  
  
1. Öffnen Sie Internet Explorer, geben Sie die folgende URL ein, und drücken Sie die EINGABETASTE:`http://localhost:8000/BlogService/GetBlog`  
  
     Die URL enthält die Basisadresse des Dienstanbieter ( `http://localhost:8000/BlogService` ), die relative Adresse des Endpunkts und den aufzurufenden Dienst Vorgang.  
  
### <a name="to-call-getblog-from-code"></a>So rufen Sie GetBlog() aus dem Code auf  
  
1. Erstellen Sie einen <xref:System.Xml.XmlReader> mit der Basisadresse und der Methode, die Sie aufrufen.  
  
     [!code-csharp[htAtomBasic#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/snippets.cs#9)]
     [!code-vb[htAtomBasic#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/snippets.vb#9)]  
  
2. Rufen Sie die statische <xref:System.ServiceModel.Syndication.SyndicationFeed.Load%28System.Xml.XmlReader%29>-Methode auf, und übergeben Sie dabei den gerade erstellten <xref:System.Xml.XmlReader>.  
  
     [!code-csharp[htAtomBasic#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/snippets.cs#10)]
     [!code-vb[htAtomBasic#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/snippets.vb#10)]  
  
     Dies ruft einen Dienstvorgang auf und füllt einen neuen <xref:System.ServiceModel.Syndication.SyndicationFeed> mit dem vom Dienstvorgang zurückgegebenen Formatierungsprogramm auf.  
  
3. Greifen Sie auf das Feedobjekt zu.  
  
     [!code-csharp[htAtomBasic#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/snippets.cs#11)]
     [!code-vb[htAtomBasic#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/snippets.vb#11)]  
  
## <a name="example"></a>Beispiel  
 Unten ist die vollständige Codeauflistung für dieses Beispiel angegeben.  
  
 [!code-csharp[htAtomBasic#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatombasic/cs/program.cs#12)]
 [!code-vb[htAtomBasic#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatombasic/vb/program.vb#12)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Verweisen Sie beim Kompilieren des obigen Codes auf System.ServiceModel.dll und System.ServiceModel.Web.dll.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.WebHttpBinding>
- <xref:System.ServiceModel.Web.WebGetAttribute>
