---
title: "Gewusst wie: Anpassen des Datenbindungsverhaltens (WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF Data Services, Anpassen"
  - "WCF Data Services, Datenbindung"
ms.assetid: 40476b89-8941-4771-8d21-2fe430c85a9d
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Gewusst wie: Anpassen des Datenbindungsverhaltens (WCF Data Services)
Mit [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] können Sie benutzerdefinierte Logik angeben, die von der <xref:System.Data.Services.Client.DataServiceCollection%601> aufgerufen wird, wenn ein Objekt hinzugefügt oder aus der Bindungsauflistung entfernt wird oder wenn eine Eigenschaftenänderung erkannt wird.  Diese benutzerdefinierte Logik wird als Methoden bereitgestellt, auf die als <xref:System.Func%602>\-Delegaten verwiesen wird, die den Wert `false` zurückgeben, wenn das Standardverhalten selbst dann ausgeführt werden soll, wenn die benutzerdefinierte Methode abgeschlossen wird und `true`, wenn die nachfolgende Verarbeitung des Ereignisses gestoppt werden soll.  
  
 In den Beispielen in diesem Thema werden benutzerdefinierte Methoden für die Parameter `entityChanged` und `entityCollectionChanged` von <xref:System.Data.Services.Client.DataServiceCollection%601> angegeben.  In den Beispielen in diesem Thema werden der Northwind\-Beispieldatendienst und automatisch generierte Clientdatendienstklassen verwendet.  Dieser Dienst und die Clientdatenklassen werden erstellt, wenn Sie den [WCF Data Services\-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) ausführen.  
  
## Beispiel  
 Die folgende Code\-Behind\-Seite für die XAML\-Datei erstellt eine <xref:System.Data.Services.Client.DataServiceCollection%601>\-Instanz mit benutzerdefinierten Methoden, die aufgerufen werden, wenn Änderungen an Daten auftreten, die an die Bindungssammlung gebunden sind.  Wenn das <xref:System.Collections.ObjectModel.ObservableCollection%601.CollectionChanged>\-Ereignis eintritt, verhindert die angegebene Methode, dass ein aus der Bindungsauflistung entferntes Element aus dem Datendienst gelöscht wird.  Wenn das <xref:System.Collections.ObjectModel.ObservableCollection%601.PropertyChanged>\-Ereignis eintritt, wird der `ShipDate`\-Wert überprüft, um sicherzustellen, dass keine Änderungen an bereits ausgelieferten Bestellungen vorgenommen werden.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderscustom.xaml.cs#wpfdatabindingcustom)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderscustom.xaml.vb#wpfdatabindingcustom)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderscustom2.xaml.vb#wpfdatabindingcustom)]  
  
## Beispiel  
 Mit dem folgenden XAML\-Code wird das Fenster für das vorherige Beispiel definiert.  
  
 [!code-xml[Astoria Northwind Client#WpfDataBindingCustomXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderscustom.xaml#wpfdatabindingcustomxaml)]  
  
## Siehe auch  
 [WCF Data Services\-Clientbibliothek](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)