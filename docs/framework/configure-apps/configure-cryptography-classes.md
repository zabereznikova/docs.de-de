---
title: Konfigurieren kryptografischer Klassen
ms.date: 03/30/2017
helpviewer_keywords:
- configuration files [.NET Framework], cryptography
- cryptographic algorithms
- security [.NET Framework], encryption
- cryptography, classes
- .NET Framework application configuration, cryptography
- default cryptography
ms.assetid: eee3ccb8-2c0d-4f35-b38d-6892a46c14e5
ms.openlocfilehash: e53f4c5c9e24fb25b43b7f27b80ab984214eeac2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "69927775"
---
# <a name="configuring-cryptography-classes"></a>Konfigurieren kryptografischer Klassen
Der Windows SDK ermöglicht es Computer Administratoren, die standardmäßigen Kryptografiealgorithmen und Algorithmusimplementierungen zu konfigurieren, die von den .NET Framework und entsprechend geschriebenen Anwendungen verwendet werden.  Beispielsweise kann ein Unternehmen, das über eine eigene Implementierung eines kryptografischen Algorithmus verfügt, diese Implementierung als Standardwert anstelle der in der Windows SDK gelieferten Implementierung festlegen. Obwohl verwaltete Anwendungen, die Kryptografie verwenden, immer eine explizite Bindung an eine bestimmte Implementierung treffen können, empfiehlt es sich, kryptografieobjekte mithilfe des kryptografiekonfigurationssystems zu erstellen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Zuordnen von Algorithmennamen zu kryptografischen Klassen](map-algorithm-names-to-cryptography-classes.md)  
 Beschreibt, wie ein Algorithmusname einer Kryptografieklasse zugeordnet wird.  
  
 [Zuordnen von Objektbezeichnern zu kryptografischen Algorithmen](map-object-identifiers-to-cryptography-algorithms.md)  
 Beschreibt, wie ein Objekt Bezeichner einem Kryptografiealgorithmus zugeordnet wird.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Kryptografiedienste](../../standard/security/cryptographic-services.md)  
 Bietet eine Übersicht über die Kryptografiedienste, die von der Windows SDK bereitgestellt werden.  
  
 [Schema für Kryptografieeinstellungen](./file-schema/cryptography/index.md)  
 Beschreibt die Elemente, mit denen angezeigte Algorithmusnamen Klassen zugeordnet werden, die Kryptografiealgorithmen implementieren.
