---
title: Lokalisierung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- culture, localization
- application development [.NET Framework], localization
- globalization [.NET Framework], localization
- code blocks
- international applications [.NET Framework], localization
- global applications, localization
- world-ready applications, localization
- user interface blocks
- localization [.NET Framework], about localization
- localizing resources
ms.assetid: 49d520d7-92d7-44ee-bb24-8b615db1d41b
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4aaf2da77a1fab55cbebd6bfa05a2b1c74e5cbbd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="localization"></a>Lokalisierung
Lokalisierung ist der Prozess der Übersetzung der Ressourcen einer Anwendung in lokalisierten Versionen für jede Kultur, die die Anwendung unterstützt. Sie sollten mit dem Lokalisierung Schritt fortfahren, erst nach dem Ausführen der [Lokalisierbarkeit](../../../docs/standard/globalization-localization/localizability-review.md) Schritt, um sicherzustellen, dass die globalisierte Anwendung für die Lokalisierung bereit ist.  
  
 Anwendung für die Lokalisierung bereit ist, wird in zwei grundlegende Blöcke, ein Block, der alle Elemente der Benutzeroberfläche enthält und einen Block mit ausführbarem Code getrennt. Der Benutzer-Schnittstelle-Block enthält nur lokalisierbare Benutzeroberflächenelemente wie z. B. Zeichenfolgen, Fehlermeldungen, Dialogfelder, Menüs, eingebettete Objektressourcen, und so weiter für die neutrale Kultur. Der Codeblock enthält nur den Anwendungscode, die von allen unterstützten Kulturen verwendet werden. Die common Language Runtime unterstützt eine Satellitenassembly-Ressourcenmodell, das ausführbaren Code einer Anwendung von den Ressourcen trennt. Weitere Informationen zum Implementieren dieses Modells finden Sie unter [Ressourcen in Desktop-Apps](../../../docs/framework/resources/index.md).  
  
 Fügen Sie für jede lokalisierte Version der Anwendung eine neue Satellitenassembly, die den lokalisierten Schnittstelle-Block in der entsprechenden Sprache für die Zielkultur übersetzt enthält. Der Codeblock für alle Kulturen sollten identisch sein. Die Kombination einer lokalisierten Version des Blocks Schnittstelle Benutzer mit der Codeblock erzeugt eine lokalisierte Version der Anwendung.  
  
 Die [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] stellt das Windows Forms Resource Editor (Winres.exe), die Sie zum Lokalisieren von Windows Forms für Ziel Kulturen schnell ermöglicht. Informationen zur Verwendung dieses Tools finden Sie unter [Winres.exe (Windows Forms Resource Editor)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Globalisierung und Lokalisierung](../../../docs/standard/globalization-localization/index.md)  
 [Überprüfung der Lokalisierbarkeit](../../../docs/standard/globalization-localization/localizability-review.md)  
 [Globalisierung](../../../docs/standard/globalization-localization/globalization.md)  
 [Ressourcen in Desktop-Apps](../../../docs/framework/resources/index.md)
