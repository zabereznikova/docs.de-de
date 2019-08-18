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
ms.openlocfilehash: 77f26405792ac782f2a04e174e8165a09b7f22f6
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2019
ms.locfileid: "69567332"
---
# <a name="configuring-cryptography-classes"></a>Konfigurieren kryptografischer Klassen
Der Windows SDK ermöglicht es Computer Administratoren, die standardmäßigen Kryptografiealgorithmen und Algorithmusimplementierungen zu konfigurieren, die von den .NET Framework und entsprechend geschriebenen Anwendungen verwendet werden.  Beispielsweise kann ein Unternehmen, das über eine eigene Implementierung eines kryptografischen Algorithmus verfügt, diese Implementierung als Standardwert anstelle der in der Windows SDK gelieferten Implementierung festlegen. Obwohl verwaltete Anwendungen, die Kryptografie verwenden, immer eine explizite Bindung an eine bestimmte Implementierung treffen können, empfiehlt es sich, kryptografieobjekte mithilfe des kryptografiekonfigurationssystems zu erstellen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Zuordnen von Algorithmennamen zu kryptografischen Klassen](../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md)  
 Beschreibt, wie ein Algorithmusname einer Kryptografieklasse zugeordnet wird.  
  
 [Zuordnen von Objektbezeichnern zu kryptografischen Algorithmen](../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)  
 Beschreibt, wie ein Objekt Bezeichner einem Kryptografiealgorithmus zugeordnet wird.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)  
 Bietet eine Übersicht über die Kryptografiedienste, die von der Windows SDK bereitgestellt werden.  
  
 [Cryptography Settings Schema (Schema für Kryptografieeinstellungen)](../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 Beschreibt die Elemente, mit denen angezeigte Algorithmusnamen Klassen zugeordnet werden, die Kryptografiealgorithmen implementieren.
