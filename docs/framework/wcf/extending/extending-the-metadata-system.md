---
title: Erweitern des Metadatensystems
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: extending metadata [WCF]
ms.assetid: 8c6b3b00-61b8-4589-8fa5-546cc33719bf
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cab59f5ddebdcc1e50921d5540d411e32b562341
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="extending-the-metadata-system"></a>Erweitern des Metadatensystems
Beim Metadatensystem von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] handelt es sich um eine Gruppe von Klassen und Schnittstellen, die Metadaten darstellen, die zum Implementieren von dienstbasierten Anwendungen erforderlich sind. Ändern bzw. erweitern Sie die Klassen, oder implementieren und konfigurieren Sie die Schnittstellen, um benutzerdefinierte Metadaten wie WDSL-Erweiterungen (Web Services Description Language) oder benutzerdefinierte WS-PolicyAttachments-Assertionen zu exportieren oder zu importieren.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Exportieren von benutzerdefinierten Metadaten für einen WCF-Erweiterung](../../../../docs/framework/wcf/extending/exporting-custom-metadata-for-a-wcf-extension.md)  
 Beschreibt die Implementierung und Verwendung der <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType>-Schnittstelle zur Einbettung benutzerdefinierter Richtlinienassertionen in WSDL-Dokumente.  
  
 [Importieren von benutzerdefinierten Metadaten für einen WCF-Erweiterung](../../../../docs/framework/wcf/extending/importing-custom-metadata-for-a-wcf-extension.md)  
 Beschreibt die Implementierung und Verwendung der <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType>-Schnittstelle zum Lesen und Beantworten benutzerdefinierter Richtlinienassertionen in WSDL-Dokumenten.  
  
 [Veröffentlichen und Abrufen von Metadaten über eine benutzerdefinierte Bindung](../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 Beschreibt, wie Metadaten über benutzerdefinierte Bindungen ausgetauscht werden.
