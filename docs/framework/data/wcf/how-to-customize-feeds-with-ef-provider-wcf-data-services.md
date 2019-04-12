---
title: 'Vorgehensweise: Anpassen von Feeds mit dem Entity Framework-Anbieter (WCF Data Services)'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, customizing
- WCF Data Services, customizing feeds
ms.assetid: fd16272e-36f2-415e-850e-8a81f2b17525
ms.openlocfilehash: 9770527f41b4981e63d65f27c409b2ce5583d2cc
ms.sourcegitcommit: 680a741667cf6859de71586a0caf6be14f4f7793
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59517212"
---
# <a name="how-to-customize-feeds-with-the-entity-framework-provider-wcf-data-services"></a>Vorgehensweise: Anpassen von Feeds mit dem Entity Framework-Anbieter (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] ermöglicht es Ihnen, die Atom-Serialisierung in einer Datendienstantwort anzupassen, damit Eigenschaften einer Entität nicht verwendeten Elementen zugeordnet werden können, die im AtomPub-Protokoll definiert werden. In diesem Thema wird gezeigt, wie Zuordnungsattribute für die Entitätstypen in einem Datenmodell definiert werden, das in einer EDMX-Datei mit dem Entity Framework-Anbieter definiert wird. Weitere Informationen finden Sie unter [Feed Anpassung](../../../../docs/framework/data/wcf/feed-customization-wcf-data-services.md).  
  
 In diesem Thema ändern Sie die Tool-generierte EDMX-Datei, die das Datenmodell enthält, manuell. Sie müssen die Datei manuell ändern, da Erweiterungen des Datenmodells nicht vom Entity Designer unterstützt werden. Weitere Informationen zu der EDMX-Datei, die die Entity Data Model-Tools zu generieren, finden Sie unter [EDMX-Datei (Entity Framework) Übersicht über die](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)). Im Beispiel in diesem Thema werden der Northwind-Beispieldatendienst und automatisch generierte Client-Datendienstklassen verwendet. Dieser Dienst und die clientdatenklassen werden erstellt, wenn Sie die [WCF Data Services-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
### <a name="to-manually-modify-the-northwindedmx-file-to-add-feed-customization-attributes"></a>So ändern Sie manuell die Datei Northwind.edmx, um Feedanpassungsattribute hinzuzufügen  
  
1. In **Projektmappen-Explorer**, mit der rechten Maustaste die `Northwind.edmx` Datei, und klicken Sie dann auf **Öffnen mit**.  
  
2. In der **Öffnen mit - Northwind.edmx** wählen Sie im Dialogfeld **XML-Editor**, und klicken Sie dann auf **OK**.  
  
3. Suchen Sie das `ConceptualModels`-Element, und ersetzen Sie den vorhandenen `Customers`-Entitätstyp durch das folgende Element, das Feedanpassungszuordnungsattribute enthält:  
  
     [!code-xml[Astoria Custom Feeds#EdmFeedCustomers](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_custom_feeds/xml/northwind.csdl#edmfeedcustomers)]  
  
4. Speichern Sie die Änderungen, und schließen Sie die Datei Northwind.edmx.  
  
5. (Optional) Mit der rechten Maustaste in der Datei Northwind.edmx, und klicken Sie dann auf **benutzerdefiniertes Tool ausführen**.  
  
     Hierdurch wird die Objektebenendatei erneut erstellt, was möglicherweise erforderlich ist.  
  
6. Kompilieren Sie das Projekt neu.  
  
## <a name="example"></a>Beispiel  
 Das vorherige Beispiel gibt das folgende Ergebnis für den URI `http://myservice/Northwind.svc/Customers('ALFKI')` zurück.  
  
 [!code-xml[Astoria Custom Feeds#EdmFeedResult](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_custom_feeds/xml/edmfeedresult.xml#edmfeedresult)]  
  
## <a name="see-also"></a>Siehe auch

- [Entity Framework-Anbieter](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)
