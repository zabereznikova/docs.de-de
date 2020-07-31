---
title: 'Entschärfung: PNG-Bilder in Symbolobjekten'
description: In diesem Artikel erfahren Sie, wie Sie das Verhalten von PNG-Frames in Symbolobjekten konfigurieren, wenn das neue Verhalten, das in .NET Framework 4.6 und höher enthalten ist, nicht erwünscht ist.
ms.date: 03/30/2017
ms.assetid: ca87fefb-7144-4b4e-8832-5a939adbb4b2
ms.openlocfilehash: b7ba2951a38ee2d1c7a9b1fc45c5a81d24986a85
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475436"
---
# <a name="mitigation-png-frames-in-icon-objects"></a><span data-ttu-id="277e3-103">Entschärfung: PNG-Bilder in Symbolobjekten</span><span class="sxs-lookup"><span data-stu-id="277e3-103">Mitigation: PNG Frames in Icon Objects</span></span>
<span data-ttu-id="277e3-104">Ab .NET Framework 4.6 konvertiert die <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> -Methode Symbole mit PNG-Bildern erfolgreich in <xref:System.Drawing.Bitmap> -Objekte.</span><span class="sxs-lookup"><span data-stu-id="277e3-104">Starting with the .NET Framework 4.6, the <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> method successfully converts icons with PNG frames into <xref:System.Drawing.Bitmap> objects.</span></span>  
  
 <span data-ttu-id="277e3-105">In Apps, die auf .NET Framework 4.5.2 und frühere Versionen ausgerichtet sind, löst die <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> -Methode eine <xref:System.ArgumentOutOfRangeException> -Ausnahme aus, wenn das <xref:System.Drawing.Icon> -Objekt PNG-Bilder aufweist.</span><span class="sxs-lookup"><span data-stu-id="277e3-105">In apps that target the .NET Framework 4.5.2 and earlier versions, the <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> method throws an <xref:System.ArgumentOutOfRangeException> exception if the <xref:System.Drawing.Icon> object has PNG frames.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="277e3-106">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="277e3-106">Impact</span></span>  
 <span data-ttu-id="277e3-107">Diese Änderung betrifft Apps, die neu kompiliert werden, um sie auf .NET Framework 4.6 auszurichten, und die eine spezielle Behandlung für die <xref:System.ArgumentOutOfRangeException> implementieren, die ausgelöst wird, wenn ein <xref:System.Drawing.Icon> -Objekt PNG-Bilder aufweist.</span><span class="sxs-lookup"><span data-stu-id="277e3-107">This change affects apps that are recompiled to target the .NET Framework 4.6 and that implement special handling for the <xref:System.ArgumentOutOfRangeException> that is thrown when an <xref:System.Drawing.Icon> object has PNG frames.</span></span> <span data-ttu-id="277e3-108">Bei der Ausführung unter .NET Framework 4.6 wird die Konvertierung erfolgreich durchgeführt und eine <xref:System.ArgumentOutOfRangeException> wird nicht mehr ausgelöst. Daher wird der Ausnahmehandler nicht mehr aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="277e3-108">When running under the .NET Framework 4.6, the conversion is successful, an <xref:System.ArgumentOutOfRangeException> is no longer thrown, and therefore the exception handler is no longer invoked.</span></span>  
  
### <a name="mitigation"></a><span data-ttu-id="277e3-109">Minderung</span><span class="sxs-lookup"><span data-stu-id="277e3-109">Mitigation</span></span>  
 <span data-ttu-id="277e3-110">Wenn dieses Verhalten nicht erwünscht ist, können Sie das vorherige Verhalten beibehalten, indem Sie das folgende Element zum Abschnitt [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) Ihrer app.config-Datei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="277e3-110">If this behavior is undesirable, you can retain the previous behavior by adding the following element to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of your app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides
      value="Switch.System.Drawing.DontSupportPngFramesInIcons=true" />  
```  
  
 <span data-ttu-id="277e3-111">Wenn die Datei „app.config“ bereits das `AppContextSwitchOverrides`-Element enthält, muss der neue Wert wie folgt mit dem `value`-Attribut zusammengeführt werden:</span><span class="sxs-lookup"><span data-stu-id="277e3-111">If the app.config file already contains the `AppContextSwitchOverrides` element, the new value should be merged with the `value` attribute like this:</span></span>  
  
```xml  
<AppContextSwitchOverrides
      value="Switch.System.Drawing.DontSupportPngFramesInIcons=true;previous key=previous-value" />
```
  
## <a name="see-also"></a><span data-ttu-id="277e3-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="277e3-112">See also</span></span>

- [<span data-ttu-id="277e3-113">Anwendungskompatibilität</span><span class="sxs-lookup"><span data-stu-id="277e3-113">Application compatibility</span></span>](application-compatibility.md)
