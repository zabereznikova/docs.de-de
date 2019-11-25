---
title: Aktualisieren des Datendiensts (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, changing data
- WCF Data Services, client library
ms.assetid: 00d993be-ffed-4dea-baf7-6eea982cdb54
ms.openlocfilehash: 02bcb8f12cd7f230d60c3b3c58174a54405ff955
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975116"
---
# <a name="updating-the-data-service-wcf-data-services"></a>Aktualisieren des Datendiensts (WCF Data Services)
Wenn Sie die [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Client Bibliothek verwenden, um einen Open Data Protocol (odata)-Feed zu nutzen, übersetzt die Bibliothek die Einträge im Feed in Instanzen von Client Datendienst Klassen. Diese Datendienstklassen werden mithilfe des <xref:System.Data.Services.Client.DataServiceContext> verfolgt, zu dem die <xref:System.Data.Services.Client.DataServiceQuery%601> gehört. Der Client verfolgt Änderungen an Entitäten nach, die mit Methoden des <xref:System.Data.Services.Client.DataServiceContext> gemeldet werden. Mithilfe dieser Methoden kann der Client hinzugefügte und gelöschte Entitäten sowie Änderungen an den Eigenschaftswerten oder an Beziehungen zwischen Entitätsinstanzen verfolgen. Wenn Sie die <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>-Methode aufrufen, werden diese nachverfolgten Änderungen als REST-basierte Vorgänge an den Datendienst zurückgesendet.  
  
> [!NOTE]
> Wenn Sie mithilfe einer Instanz von <xref:System.Data.Services.Client.DataServiceCollection%601> Daten an Steuerelemente binden, werden die an Daten im gebundenen Steuerelement vorgenommenen Änderungen automatisch dem <xref:System.Data.Services.Client.DataServiceContext> gemeldet. Weitere Informationen finden Sie unter [Binden von Daten an Steuerelemente](binding-data-to-controls-wcf-data-services.md).  
  
## <a name="adding-modifying-and-changing-entities"></a>Hinzufügen und Ändern von Entitäten  
 Wenn Sie das Dialogfeld " **Dienstverweis hinzufügen** " in Visual Studio zum Hinzufügen eines Verweises zu einem odata-Feed verwenden, verfügen die resultierenden Client Datendienst Klassen jeweils über eine statische *Create* -Methode, die einen Parameter für jede Entitäts Eigenschaft verwendet, die keine NULL-Werte zulässt. Sie können mithilfe dieser Methode Instanzen von Entitätstypklassen wie im folgenden Beispiel erstellen:  
  
 [!code-csharp[Astoria Northwind Client#CreateNewProduct](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#createnewproduct)]
 [!code-vb[Astoria Northwind Client#CreateNewProduct](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#createnewproduct)]  
  
 Um eine Entitäts Instanz hinzuzufügen, müssen Sie die entsprechende *AddTo* -Methode für die <xref:System.Data.Services.Client.DataServiceContext> Klasse, die vom Dialogfeld **Dienstverweis hinzufügen** generiert wird, wie im folgenden Beispiel gezeigt:  
  
 [!code-csharp[Astoria Northwind Client#AddProductSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addproductspecific)]
 [!code-vb[Astoria Northwind Client#AddProductSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addproductspecific)]  
  
 Diese fügt das Objekt zum Kontext und in die richtige Entitätenmenge hinzu. Sie können auch <xref:System.Data.Services.Client.DataServiceContext.AddObject%2A> aufrufen, Sie müssen jedoch stattdessen den Entitätenmengennamen angeben. Wenn die hinzugefügte Entität über eine oder mehrere Beziehungen zu anderen Entitäten verfügt, können Sie entweder die <xref:System.Data.Services.Client.DataServiceContext.AddRelatedObject%2A>-Methode verwenden, oder Sie verwenden eine der vorherigen Methoden und definieren die Links auch explizit. Diese Vorgänge werden weiter unten in diesem Thema erläutert.  
  
 Zum Ändern einer vorhandenen Instanz einer Entität führen Sie zunächst eine Abfrage für die entsprechende Entität durch und nehmen die gewünschten Änderungen an den zugehörigen Eigenschaften vor. Rufen Sie anschließend die <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A>-Methode für den <xref:System.Data.Services.Client.DataServiceContext> auf, um der Clientbibliothek mitzuteilen, dass eine Aktualisierung für dieses Objekt gesendet werden muss, wie im folgenden Beispiel dargestellt:  
  
 [!code-csharp[Astoria Northwind Client#ModifyCustomerSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#modifycustomerspecific)]
 [!code-vb[Astoria Northwind Client#ModifyCustomerSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#modifycustomerspecific)]  
  
 Zum Löschen einer Entitätsinstanz rufen Sie wie im folgenden Beispiel dargestellt die <xref:System.Data.Services.Client.DataServiceContext.DeleteObject%2A>-Methode für den <xref:System.Data.Services.Client.DataServiceContext> auf:  
  
 [!code-csharp[Astoria Northwind Client#DeleteProductSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#deleteproductspecific)]
 [!code-vb[Astoria Northwind Client#DeleteProductSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#deleteproductspecific)]  
  
 Weitere Informationen finden Sie unter Gewusst [wie: Hinzufügen, ändern und Löschen von Entitäten](how-to-add-modify-and-delete-entities-wcf-data-services.md).  
  
## <a name="attaching-entities"></a>Anfügen von Entitäten  
 Mithilfe der Clientbibliothek können Sie an einer Entität vorgenommene Aktualisierungen speichern, ohne zuerst eine Abfrage zum Laden der Entität in den <xref:System.Data.Services.Client.DataServiceContext> auszuführen. Verwenden Sie die <xref:System.Data.Services.Client.DataServiceContext.AttachTo%2A>-Methode, um ein vorhandenes Objekt an eine bestimmte Entitätenmenge im <xref:System.Data.Services.Client.DataServiceContext> anzufügen. Sie können dann das Objekt ändern und die Änderungen am Datendienst speichern. Im folgenden Beispiel wird ein geändertes Kundenobjekt an den Kontext angefügt, und dann wird <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A> aufgerufen, um das angefügte Objekt als <xref:System.Data.Services.Client.EntityStates.Modified> zu markieren, bevor <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> aufgerufen wird:  
  
 [!code-csharp[Astoria Northwind Client#AttachObjectSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#attachobjectspecific)]
 [!code-vb[Astoria Northwind Client#AttachObjectSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#attachobjectspecific)]  
  
 Folgendes gilt beim Anfügen von Objekten:  
  
- Ein Objekt wird im <xref:System.Data.Services.Client.EntityStates.Unchanged>-Zustand angefügt.  
  
- Wenn ein Objekt angefügt wird, werden Objekte, die sich auf das angefügte Objekt beziehen, nicht auch angefügt.  
  
- Ein Objekt kann nicht angefügt werden, wenn die Entität bereits vom Kontext verfolgt wird.  
  
- Die <xref:System.Data.Services.Client.DataServiceContext.AttachTo%28System.String%2CSystem.Object%2CSystem.String%29>-Methodenüberladung, die einen `etag`-Parameter annimmt, wird verwendet, wenn Sie ein zusammen mit einem eTag-Wert empfangenes Entitätsobjekt anfügen. Dieser eTag-Wert wird dann zur Überprüfung auf Parallelität verwendet, wenn Änderungen am angefügten Objekt gespeichert werden.  
  
 Weitere Informationen finden Sie unter Gewusst [wie: Anfügen einer vorhandenen Entität an den DataServiceContext](attach-an-existing-entity-to-dc-wcf-data.md).  
  
## <a name="creating-and-modifying-relationship-links"></a>Erstellen und Ändern von Beziehungslinks  
 Wenn Sie eine neue Entität mit der <xref:System.Data.Services.Client.DataServiceContext.AddObject%2A>-Methode oder der entsprechenden *AddTo* -Methode der <xref:System.Data.Services.Client.DataServiceContext>-Klasse hinzufügen, die das Dialogfeld **Dienstverweis hinzufügen** generiert, werden alle Beziehungen zwischen der neuen Entität und den zugehörigen Entitäten nicht automatisch definiert.  
  
 Sie können Beziehungen zwischen Entitätsinstanzen erstellen und ändern und die Clientbibliothek diese Änderungen im Datendienst widerspiegeln lassen. Beziehungen zwischen Entitäten werden im Modell als Zuordnungen definiert, und das <xref:System.Data.Services.Client.DataServiceContext>-Objekt verfolgt jede Beziehung als Linkobjekt im Kontext. [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] stellt die folgenden Methoden für die <xref:System.Data.Services.Client.DataServiceContext>-Klasse bereit, um diese Links zu erstellen, zu ändern und zu löschen:  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|<xref:System.Data.Services.Client.DataServiceContext.AddRelatedObject%2A>|Erstellt einen neuen Link zwischen zwei verknüpften Entitätsobjekten. Das Aufrufen dieser Methode entspricht dem Aufrufen von <xref:System.Data.Services.Client.DataServiceContext.AddObject%2A> und <xref:System.Data.Services.Client.DataServiceContext.AddLink%2A>, um das neue Objekt zu erstellen und die Beziehung zu einem vorhandenen Objekt zu definieren.|  
|<xref:System.Data.Services.Client.DataServiceContext.AddLink%2A>|Erstellt einen neuen Link zwischen zwei verknüpften Entitätsobjekten.|  
|<xref:System.Data.Services.Client.DataServiceContext.SetLink%2A>|Aktualisiert einen vorhandenen Link zwischen zwei verknüpften Entitätsobjekten. <xref:System.Data.Services.Client.DataServiceContext.SetLink%2A> wird auch verwendet, um Links mit einer Kardinalität von 0 bzw. 1:1 (`0..1:1`) und 1:1 (`1:1`) zu löschen. Sie können dazu das verknüpfte Objekte auf `null` festlegen.|  
|<xref:System.Data.Services.Client.DataServiceContext.DeleteLink%2A>|Markiert einen Link, den der Kontext für den Löschvorgang nachverfolgt, wenn die <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>-Methode aufgerufen wird. Verwenden Sie diese Methode, wenn Sie ein verknüpftes Objekt löschen oder durch das Löschen des Links zu einem vorhandenen Objekt und dem nachfolgenden Hinzufügen eines Links zum neuen verknüpften Objekt eine Beziehung ändern.|  
|<xref:System.Data.Services.Client.DataServiceContext.AttachLink%2A>|Benachrichtigt den Kontext über einen vorhandenen Link zwischen zwei Entitätsobjekten. Der Kontext geht davon aus, dass diese Beziehung bereits im Datendienst vorhanden ist, und versucht nicht, den Link zu erstellen, wenn Sie die <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>-Methode aufrufen. Verwenden Sie diese Methode, wenn Sie Objekte an einen Kontext anfügen und außerdem den Link zwischen beiden anfügen müssen. Wenn Sie eine neue Beziehung definieren, sollten Sie stattdessen <xref:System.Data.Services.Client.DataServiceContext.AddLink%2A> verwenden.|  
|<xref:System.Data.Services.Client.DataServiceContext.DetachLink%2A>|Beendet die Nachverfolgung des angegebenen Links im Kontext. Diese Methode wird verwendet, um 1:n-Beziehungen (`*:*`) zu löschen. Für Beziehungslinks mit einer Multiplizität von 1 müssen Sie stattdessen <xref:System.Data.Services.Client.DataServiceContext.SetLink%2A> verwenden.|  
  
 Im folgenden Beispiel wird gezeigt, wie die <xref:System.Data.Services.Client.DataServiceContext.AddRelatedObject%2A>-Methode verwendet wird, um ein neues `Order_Detail` hinzuzufügen, das sich auf eine vorhandene `Orders`-Entität bezieht. Da das neue `Order_Details`-Objekt jetzt vom <xref:System.Data.Services.Client.DataServiceContext> nachverfolgt wird, wird die Beziehung des hinzugefügten `Order_Details`-Objekts zur vorhandenen `Products`-Entität definiert, indem die <xref:System.Data.Services.Client.DataServiceContext.AddLink%2A>-Methode aufgerufen werden:  
  
 [!code-csharp[Astoria Northwind Client#AddOrderDetailToOrderSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addorderdetailtoorderspecific)]
 [!code-vb[Astoria Northwind Client#AddOrderDetailToOrderSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addorderdetailtoorderspecific)]  
  
 Während die <xref:System.Data.Services.Client.DataServiceContext.AddLink%2A>-Methode Links definiert, die im Datendienst erstellt werden müssen, müssen Sie auch die Navigationseigenschaften für die Objekte selbst festlegen, damit sich diese Links in den im Kontext enthaltenen Objekten widerspiegeln. Im vorherigen Beispiel sollten Sie die Navigationseigenschaften wie folgt festlegen:  
  
 [!code-csharp[Astoria Northwind Client#SetNavProps](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#setnavprops)]
 [!code-vb[Astoria Northwind Client#SetNavProps](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#setnavprops)]  
  
 Weitere Informationen finden Sie unter Gewusst [wie: Definieren von Entitäts Beziehungen](how-to-define-entity-relationships-wcf-data-services.md).  
  
## <a name="saving-changes"></a>Speichern von Änderungen  
 Änderungen werden in der <xref:System.Data.Services.Client.DataServiceContext>-Instanz nachverfolgt, jedoch nicht unmittelbar an den Server gesendet. Wenn Sie die erforderlichen Änderungen für eine bestimmte Aktivität vorgenommen haben, rufen Sie <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> auf, um alle Änderungen an den Datendienst zu übergeben. Weitere Informationen finden Sie unter [Verwalten des Datendienst Kontexts](managing-the-data-service-context-wcf-data-services.md). Sie können Änderungen mit der <xref:System.Data.Services.Client.DataServiceContext.BeginSaveChanges%2A>-Methode und der <xref:System.Data.Services.Client.DataServiceContext.EndSaveChanges%2A>-Methode auch asynchron speichern. Weitere Informationen finden Sie unter [asynchrone Vorgänge](asynchronous-operations-wcf-data-services.md).  
  
## <a name="see-also"></a>Siehe auch

- [WCF Data Services-Clientbibliothek](wcf-data-services-client-library.md)
- [Abfragen des Datendiensts](querying-the-data-service-wcf-data-services.md)
- [Asynchrone Vorgänge](asynchronous-operations-wcf-data-services.md)
- [Batchvorgänge](batching-operations-wcf-data-services.md)
- [Objektmaterialisierung](object-materialization-wcf-data-services.md)
- [Verwalten des Datendienstkontexts](managing-the-data-service-context-wcf-data-services.md)
