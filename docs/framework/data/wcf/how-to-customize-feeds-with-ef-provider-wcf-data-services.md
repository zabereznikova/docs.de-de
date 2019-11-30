---
title: 'Gewusst wie: Anpassen von Feeds mit dem Entity Framework-Anbieter (WCF Data Services)'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, customizing
- WCF Data Services, customizing feeds
ms.assetid: fd16272e-36f2-415e-850e-8a81f2b17525
ms.openlocfilehash: 16c3741068d19fb55d8acfd28e4f83df633b0b09
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569156"
---
# <a name="how-to-customize-feeds-with-the-entity-framework-provider-wcf-data-services"></a>Gewusst wie: Anpassen von Feeds mit dem Entity Framework-Anbieter (WCF Data Services)
Mit WCF Data Services können Sie die Atom-Serialisierung in einer Datendienst Antwort anpassen, sodass Eigenschaften einer Entität nicht verwendeten Elementen zugeordnet werden können, die im AtomPub-Protokoll definiert sind. In diesem Thema wird gezeigt, wie Zuordnungsattribute für die Entitätstypen in einem Datenmodell definiert werden, das in einer EDMX-Datei mit dem Entity Framework-Anbieter definiert wird. Weitere Informationen finden Sie unter [Feed-Anpassung](feed-customization-wcf-data-services.md).  
  
 In diesem Thema ändern Sie die Tool-generierte EDMX-Datei, die das Datenmodell enthält, manuell. Sie müssen die Datei manuell ändern, da Erweiterungen des Datenmodells nicht vom Entity Designer unterstützt werden. Weitere Informationen über die EDMX-Datei, die die Entity Data Model Tools generieren, finden Sie unter Übersicht über die [EDMX-Datei (Entity Framework)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)). Im Beispiel in diesem Thema werden der Northwind-Beispieldatendienst und automatisch generierte Client-Datendienstklassen verwendet. Dieser Dienst und die Client Daten Klassen werden erstellt, wenn Sie den [WCF Data Services Schnellstart](quickstart-wcf-data-services.md)ausführen.  
  
### <a name="to-manually-modify-the-northwindedmx-file-to-add-feed-customization-attributes"></a>So ändern Sie manuell die Datei Northwind.edmx, um Feedanpassungsattribute hinzuzufügen  
  
1. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf die Datei `Northwind.edmx`, und klicken Sie dann auf **Öffnen mit**.  
  
2. Wählen Sie im Dialogfeld **Öffnen mit-Northwind. edmx** den Eintrag **XML-Editor**aus, und klicken Sie dann auf **OK**.  
  
3. Suchen Sie das `ConceptualModels`-Element, und ersetzen Sie den vorhandenen `Customers`-Entitätstyp durch das folgende Element, das Feedanpassungszuordnungsattribute enthält:  
  
     [!code-xml[Astoria Custom Feeds#EdmFeedCustomers](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_custom_feeds/xml/northwind.csdl#edmfeedcustomers)]  
  
4. Speichern Sie die Änderungen, und schließen Sie die Datei Northwind.edmx.  
  
5. Optionale Klicken Sie mit der rechten Maustaste auf die Datei Northwind. edmx und dann auf **benutzerdefiniertes Tool ausführen**.  
  
     Hierdurch wird die Objektebenendatei erneut erstellt, was möglicherweise erforderlich ist.  
  
6. Kompilieren Sie das Projekt neu.  
  
## <a name="example"></a>Beispiel  
 Das vorherige Beispiel gibt das folgende Ergebnis für den URI `http://myservice/Northwind.svc/Customers('ALFKI')` zurück.  
  
 [!code-xml[Astoria Custom Feeds#EdmFeedResult](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_custom_feeds/xml/edmfeedresult.xml#edmfeedresult)]  
  
## <a name="see-also"></a>Siehe auch

- [Entity Framework-Anbieter](entity-framework-provider-wcf-data-services.md)
