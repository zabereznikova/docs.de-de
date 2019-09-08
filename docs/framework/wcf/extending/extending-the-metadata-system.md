---
title: Erweitern des Metadatensystems
ms.date: 03/30/2017
helpviewer_keywords:
- extending metadata [WCF]
ms.assetid: 8c6b3b00-61b8-4589-8fa5-546cc33719bf
ms.openlocfilehash: d3ce7e1a228e6303be1009c7b72f4e889b40c536
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795721"
---
# <a name="extending-the-metadata-system"></a>Erweitern des Metadatensystems
Das Windows Communication Foundation (WCF)-Metadatensystem ist eine Gruppe von Klassen und Schnittstellen, die Metadaten darstellen, die für die Implementierung von Dienst basierten Anwendungen erforderlich sind. Ändern bzw. erweitern Sie die Klassen, oder implementieren und konfigurieren Sie die Schnittstellen, um benutzerdefinierte Metadaten wie WDSL-Erweiterungen (Web Services Description Language) oder benutzerdefinierte WS-PolicyAttachments-Assertionen zu exportieren oder zu importieren.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Exportieren von benutzerdefinierten Metadaten für eine WCF-Erweiterung](exporting-custom-metadata-for-a-wcf-extension.md)  
 Beschreibt die Implementierung und Verwendung der <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType>-Schnittstelle zur Einbettung benutzerdefinierter Richtlinienassertionen in WSDL-Dokumente.  
  
 [Importieren von benutzerdefinierten Metadaten für eine WCF-Erweiterung](importing-custom-metadata-for-a-wcf-extension.md)  
 Beschreibt die Implementierung und Verwendung der <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType>-Schnittstelle zum Lesen und Beantworten benutzerdefinierter Richtlinienassertionen in WSDL-Dokumenten.  
  
 [Veröffentlichen und Abrufen von Metadaten über eine benutzerdefinierte Bindung](publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 Beschreibt, wie Metadaten über benutzerdefinierte Bindungen ausgetauscht werden.
