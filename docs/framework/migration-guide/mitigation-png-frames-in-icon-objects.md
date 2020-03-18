---
title: 'Entschärfung: PNG-Bilder in Symbolobjekten'
ms.date: 03/30/2017
ms.assetid: ca87fefb-7144-4b4e-8832-5a939adbb4b2
ms.openlocfilehash: d661e45bfbbe5e1c5ca5b7eb123e71aa32a096ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "79181220"
---
# <a name="mitigation-png-frames-in-icon-objects"></a><span data-ttu-id="d066b-102">Entschärfung: PNG-Bilder in Symbolobjekten</span><span class="sxs-lookup"><span data-stu-id="d066b-102">Mitigation: PNG Frames in Icon Objects</span></span>
<span data-ttu-id="d066b-103">Ab .NET Framework 4.6 konvertiert die <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> -Methode Symbole mit PNG-Bildern erfolgreich in <xref:System.Drawing.Bitmap> -Objekte.</span><span class="sxs-lookup"><span data-stu-id="d066b-103">Starting with the .NET Framework 4.6, the <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> method successfully converts icons with PNG frames into <xref:System.Drawing.Bitmap> objects.</span></span>  
  
 <span data-ttu-id="d066b-104">In Apps für .NET Framework 4.5.2 und frühere Versionen löst die <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType>-Methode eine <xref:System.ArgumentOutOfRangeException>-Ausnahme aus, wenn das <xref:System.Drawing.Icon>-Objekt PNG-Bilder aufweist.</span><span class="sxs-lookup"><span data-stu-id="d066b-104">In apps that target the .NET Framework 4.5.2 and earlier versions, the <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> method throws an <xref:System.ArgumentOutOfRangeException> exception if the <xref:System.Drawing.Icon> object has PNG frames.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="d066b-105">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="d066b-105">Impact</span></span>  
 <span data-ttu-id="d066b-106">Diese Änderung betrifft Apps, die neu kompiliert werden, um sie auf .NET Framework 4.6 auszurichten, und die eine spezielle Behandlung für die <xref:System.ArgumentOutOfRangeException> implementieren, die ausgelöst wird, wenn ein <xref:System.Drawing.Icon> -Objekt PNG-Bilder aufweist.</span><span class="sxs-lookup"><span data-stu-id="d066b-106">This change affects apps that are recompiled to target the .NET Framework 4.6 and that implement special handling for the <xref:System.ArgumentOutOfRangeException> that is thrown when an <xref:System.Drawing.Icon> object has PNG frames.</span></span> <span data-ttu-id="d066b-107">Bei der Ausführung unter .NET Framework 4.6 wird die Konvertierung erfolgreich durchgeführt und eine <xref:System.ArgumentOutOfRangeException> wird nicht mehr ausgelöst. Daher wird der Ausnahmehandler nicht mehr aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="d066b-107">When running under the .NET Framework 4.6, the conversion is successful, an <xref:System.ArgumentOutOfRangeException> is no longer thrown, and therefore the exception handler is no longer invoked.</span></span>  
  
### <a name="mitigation"></a><span data-ttu-id="d066b-108">Minderung</span><span class="sxs-lookup"><span data-stu-id="d066b-108">Mitigation</span></span>  
 <span data-ttu-id="d066b-109">Wenn dieses Verhalten nicht erwünscht ist, können Sie das vorherige Verhalten beibehalten, indem Sie das folgende Element zum [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md)-Abschnitt Ihrer app.config-Datei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="d066b-109">If this behavior is undesirable, you can retain the previous behavior by adding the following element to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of your app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides
      value="Switch.System.Drawing.DontSupportPngFramesInIcons=true" />  
```  
  
 <span data-ttu-id="d066b-110">Wenn die Datei „app.config“ bereits das `AppContextSwitchOverrides`-Element enthält, muss der neue Wert wie folgt mit dem `value`-Attribut zusammengeführt werden:</span><span class="sxs-lookup"><span data-stu-id="d066b-110">If the app.config file already contains the `AppContextSwitchOverrides` element, the new value should be merged with the `value` attribute like this:</span></span>  
  
```xml  
<AppContextSwitchOverrides
      value="Switch.System.Drawing.DontSupportPngFramesInIcons=true;<previous key>=<previous value>" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="d066b-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d066b-111">See also</span></span>

- [<span data-ttu-id="d066b-112">Anwendungskompatibilität</span><span class="sxs-lookup"><span data-stu-id="d066b-112">Application compatibility</span></span>](application-compatibility.md)
