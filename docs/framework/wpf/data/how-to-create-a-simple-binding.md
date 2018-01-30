---
title: 'Gewusst wie: Erstellen einer einfachen Bindung'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 73ed25406aa398aa35c275b20da1deee48b119ab
ms.sourcegitcommit: f28752eab00d2bd97e971542c0f49ce63cfbc239
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2018
---
# <a name="how-to-create-a-simple-binding"></a>Gewusst wie: Erstellen einer einfachen Bindung
Dieses Beispiel veranschaulicht das Erstellen eines einfachen <xref:System.Windows.Data.Binding>.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel haben Sie eine `Person` Objekt mit der eine Zeichenfolgeneigenschaft, die mit dem Namen `PersonName`. Die `Person` Objekt ist im Namespace namens definiert `SDKSample`.  
  
 Das folgende Beispiel instanziiert die `Person` -Objekt mit einer `PersonName` Eigenschaftswert `Joe`. Dies erfolgt in der `Resources` Abschnitt zugewiesen, und wählen Sie eine `x:Key`.  
  
 [!code-xaml[SimpleBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml)]  
  
 Zum Binden an die `PersonName` Eigenschaft würden Sie Folgendes tun:  
  
 [!code-xaml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 Daher die <xref:System.Windows.Controls.TextBlock> wird mit dem Wert "Joe" angezeigt.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
