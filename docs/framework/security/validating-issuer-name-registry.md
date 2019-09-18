---
title: Validierung der Ausstellernamenregistration
ms.date: 03/30/2017
ms.assetid: c4644dd1-dead-48ff-abeb-7bffae69a6ac
ms.openlocfilehash: dc7da9d3dc4ab696d8c27d8e12583b8d06e747fe
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71045313"
---
# <a name="validating-issuer-name-registry"></a>Validierung der Ausstellernamenregistration
Mithilfe von "Überprüfen der Ausstellernamensregistrierung" (VINR) für Windows Identity Foundation können Anwendungen mit mehreren Mandanten sicherstellen, dass ein eingehendes Token von einem vertrauenswürdigen Mandanten und Identitätsanbieter ausgegeben wurde. Diese Funktionalität ist besonders für Anwendungen mit mehreren Mandanten nützlich, die Microsoft Azure Active Directory verwenden, da alle Token, die von Microsoft Azure AD ausgegeben werden, mit demselben Zertifikat signiert werden. Um zwischen den Anfragen mehrerer Mandanten zu unterscheiden, die das gleiche Zertifikat verwenden - und infolgedessen den gleichen Fingerabdruck haben -, muss die Anwendung den Ausstellernamen für jeden Mandanten bestehen lassen, damit die Validierungslogik ausgeführt werden kann. Die VINR stellt diese Funktion bereit und erlaubt es Ihnen außerdem, benutzerdefinierte Validierungslogik hinzufügen oder die Ausstellerregistrierungsdaten an anderen Speicherorten als in einer Konfigurationsdatei zu speichern. Die Erweiterung kann der WIF-Pipeline der Anwendung hinzugefügt werden, oder sie kann unabhängig verwendet werden.  
  
 Die VINR ist als NuGet-Paket verfügbar. Weitere Informationen finden Sie unter [Herunterladen des Pakets zur Validierung der Ausstellernamenregistration](downloading-the-validating-issuer-name-registry-package.md).  
  
## <a name="scenarios"></a>Szenarien  
 Die VINR ermöglicht folgendes Hauptszenario:  
  
- Überprüfen **eines Tokens in einer mehr**Instanzen fähigen Anwendung: In diesem Szenario hat ein Unternehmen namens Litware eine Anwendung mit mehreren Mandanten entwickelt, die einen Identitäts Anbieter wie z. b. Windows Azure AD verwendet. Diese Anwendung bedient zwei Kunden: "Configuration Manager" und "Fabrikam". Wenn ein Benutzer von Fabrikam sich bei der Anwendung von Litware authentifiziert, wird das resultierende Token von Microsoft Azure AD mit seinem Standardzertifikats signiert, und die Anfrage wird von Fabrikam ausgegeben. Die Anwendung muss überprüfen, ob der Ausstellername und das Token gültig sind, und muss sie von Anfragen von Contoso unterscheiden können, die mit demselben Zertifikat von Windows Azure AD signiert werden. Die VINR erleichtert der Litware-Anwendung die Unterscheidung und die Validierung der Anfragen von mehreren Mandanten wie Contoso und Fabrikam.  
  
## <a name="features"></a>Features  
 Die VINR bietet die folgenden Funktionen:  
  
- **Aussteller Name und tokenüberprüfung für mehr Instanzen fähige Anwendungen**: Überprüft das eingehende Token, indem der Aussteller Name (Mandant) überprüft wird und ob das Token mit einem gültigen Zertifikat des Identitäts Anbieters signiert wurde.  
  
- **Erweiterbarkeit für benutzerdefinierte Validierungs Logik und Datenspeicher**: Bietet Erweiterbarkeit, um Ihre eigene Validierungs Logik einzufügen und einen anderen Datenspeicher als die Standard Konfigurationsdatei anzugeben.
