---
ms.openlocfilehash: 668d047d3247d64cb1400d4a9ea6887795fa0d44
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804035"
---
### <a name="httprequestcontentencoding-property-prohibits-utf7"></a>HttpRequest.ContentEncoding-Eigenschaft verhindert UTF7

|   |   |
|---|---|
|Details|Ab .NET Framework 4.5 ist die UTF-7-Codierung in <xref:System.Web.HttpRequest?displayProperty=name>-Texten nicht zulässig. Teilweise treten bei Daten für Anwendungen, die von eingehenden UTF-7-Daten abhängen, Decodierungsprobleme auf.|
|Vorschlag|Im Idealfall sollten Anwendungen aktualisiert verwenden, damit sie die UTF-7-Codierung in <xref:System.Web.HttpRequest?displayProperty=name> nicht verwenden. Alternativ kann das Legacyverhalten mithilfe des <code>aspnet:AllowUtf7RequestContentEncoding</code>-Attributs des [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md)-Elements wiederhergestellt werden.|
|Bereich|Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType></li></ul>|
