---
title: 'Vorgehensweise: Anpassen des Datenbindungsverhaltens (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- WCF Data Services, data binding
ms.assetid: 40476b89-8941-4771-8d21-2fe430c85a9d
ms.openlocfilehash: f55c9790b8300a1a3f26e031a17a0982638b562b
ms.sourcegitcommit: 680a741667cf6859de71586a0caf6be14f4f7793
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59517420"
---
# <a name="how-to-customize-data-binding-behaviors-wcf-data-services"></a>Vorgehensweise: Anpassen des Datenbindungsverhaltens (WCF Data Services)
Mit [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] können Sie benutzerdefinierte Logik angeben, die von der <xref:System.Data.Services.Client.DataServiceCollection%601> aufgerufen wird, wenn ein Objekt hinzugefügt oder aus der Bindungsauflistung entfernt wird oder wenn eine Eigenschaftenänderung erkannt wird. Diese benutzerdefinierte Logik wird als Methoden bereitgestellt, als <xref:System.Func%602> Delegaten, der einen Wert zurückgeben `false` Wenn das Standardverhalten immer noch ausgeführt werden soll, wenn die benutzerdefinierte Methode abgeschlossen wird und `true` bei der Verarbeitung der nachfolgenden der Ereignis sollte beendet werden.  
  
 In den Beispielen in diesem Thema werden benutzerdefinierte Methoden für die Parameter `entityChanged` und `entityCollectionChanged` von <xref:System.Data.Services.Client.DataServiceCollection%601> angegeben. In den Beispielen in diesem Thema werden der Northwind-Beispieldatendienst und automatisch generierte Clientdatendienstklassen verwendet. Dieser Dienst und die clientdatenklassen werden erstellt, wenn Sie die [WCF Data Services-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Beispiel  
 Die folgende Code-Behind-Seite für die XAML-Datei erstellt eine <xref:System.Data.Services.Client.DataServiceCollection%601>-Instanz mit benutzerdefinierten Methoden, die aufgerufen werden, wenn Änderungen an Daten auftreten, die an die Bindungssammlung gebunden sind. Wenn das <xref:System.Collections.ObjectModel.ObservableCollection%601.CollectionChanged>-Ereignis eintritt, verhindert die angegebene Methode, dass ein aus der Bindungsauflistung entferntes Element aus dem Datendienst gelöscht wird. Wenn das <xref:System.Collections.ObjectModel.ObservableCollection%601.PropertyChanged>-Ereignis eintritt, wird der `ShipDate`-Wert überprüft, um sicherzustellen, dass keine Änderungen an bereits ausgelieferten Bestellungen vorgenommen werden.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderscustom.xaml.cs#wpfdatabindingcustom)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom.xaml.vb#wpfdatabindingcustom)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom2.xaml.vb#wpfdatabindingcustom)]  
  
## <a name="example"></a>Beispiel  
 Mit dem folgenden XAML-Code wird das Fenster für das vorherige Beispiel definiert.  
  
 [!code-xaml[Astoria Northwind Client#WpfDataBindingCustomXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom.xaml#wpfdatabindingcustomxaml)]  
  
## <a name="see-also"></a>Siehe auch

- [WCF Data Services-Clientbibliothek](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
