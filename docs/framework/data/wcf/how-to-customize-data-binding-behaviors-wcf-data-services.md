---
title: 'Vorgehensweise: Anpassen des Daten Bindungs Verhaltens (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- WCF Data Services, data binding
ms.assetid: 40476b89-8941-4771-8d21-2fe430c85a9d
ms.openlocfilehash: c878096cba7d31e0b48727213ee1bb8239b8f690
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70790752"
---
# <a name="how-to-customize-data-binding-behaviors-wcf-data-services"></a>Vorgehensweise: Anpassen des Daten Bindungs Verhaltens (WCF Data Services)
Mit [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] können Sie benutzerdefinierte Logik angeben, die von der <xref:System.Data.Services.Client.DataServiceCollection%601> aufgerufen wird, wenn ein Objekt hinzugefügt oder aus der Bindungsauflistung entfernt wird oder wenn eine Eigenschaftenänderung erkannt wird. Diese benutzerdefinierte Logik wird als Methoden bereitgestellt, <xref:System.Func%602> auf `false` die als Delegaten verwiesen wird, die den Wert zurückgeben, wenn das Standardverhalten weiterhin ausgeführt werden `true` soll, wenn die benutzerdefinierte Methode abgeschlossen wird und wenn die nachfolgende Verarbeitung des das Ereignis sollte beendet werden.  
  
 In den Beispielen in diesem Thema werden benutzerdefinierte Methoden für die Parameter `entityChanged` und `entityCollectionChanged` von <xref:System.Data.Services.Client.DataServiceCollection%601> angegeben. In den Beispielen in diesem Thema werden der Northwind-Beispieldatendienst und automatisch generierte Clientdatendienstklassen verwendet. Dieser Dienst und die Client Daten Klassen werden erstellt, wenn Sie den [WCF Data Services Schnellstart](quickstart-wcf-data-services.md)ausführen.  
  
## <a name="example"></a>Beispiel  
 Die folgende Code-Behind-Seite für die XAML-Datei erstellt eine <xref:System.Data.Services.Client.DataServiceCollection%601>-Instanz mit benutzerdefinierten Methoden, die aufgerufen werden, wenn Änderungen an Daten auftreten, die an die Bindungssammlung gebunden sind. Wenn das <xref:System.Collections.ObjectModel.ObservableCollection%601.CollectionChanged>-Ereignis eintritt, verhindert die angegebene Methode, dass ein aus der Bindungsauflistung entferntes Element aus dem Datendienst gelöscht wird. Wenn das <xref:System.Collections.ObjectModel.ObservableCollection%601.PropertyChanged>-Ereignis eintritt, wird der `ShipDate`-Wert überprüft, um sicherzustellen, dass keine Änderungen an bereits ausgelieferten Bestellungen vorgenommen werden.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderscustom.xaml.cs#wpfdatabindingcustom)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom.xaml.vb#wpfdatabindingcustom)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom2.xaml.vb#wpfdatabindingcustom)]  
  
## <a name="example"></a>Beispiel  
 Mit dem folgenden XAML-Code wird das Fenster für das vorherige Beispiel definiert.  
  
 [!code-xaml[Astoria Northwind Client#WpfDataBindingCustomXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom.xaml#wpfdatabindingcustomxaml)]  
  
## <a name="see-also"></a>Siehe auch

- [WCF Data Services-Clientbibliothek](wcf-data-services-client-library.md)
