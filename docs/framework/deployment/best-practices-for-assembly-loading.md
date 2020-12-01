---
title: Bewährte Methoden für das Laden von Assemblys
description: Erkunden Sie bewährte Methoden für das Laden von Assemblys in .NET. Vermeiden Sie Probleme mit Typidentität, die zu ungültigen Umwandlungen, fehlenden Methoden und anderen Ausnahmen führen können.
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies,binding
- LoadFrom method
- default load context
- TypeLoadException class,causes
- assembly loading errors
- load contexts
- assemblies,loading
- LoadWithPartialName method
- load-from context
ms.assetid: 68d1c539-6a47-4614-ab59-4b071c9d4b4c
ms.openlocfilehash: 9e09c9e43a4bd8b13712d5fbbf85830394ac0b58
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236441"
---
# <a name="best-practices-for-assembly-loading"></a>Bewährte Methoden für das Laden von Assemblys

In diesem Artikel werden Möglichkeiten zur Vermeidung von Problemen mit der Typidentität erläutert, die zu <xref:System.InvalidCastException>, <xref:System.MissingMethodException> und anderen Fehlern führen können. In diesem Artikel werden folgende Empfehlungen besprochen:  
  
- [Vor- und Nachteile von Load-Kontexten](#load_contexts)  
  
- [Vermeiden von Bindungen bei partiellen Assemblynamen](#avoid_partial_names)  
  
- [Vermeiden des Ladens von Assemblys in mehrere Kontexte](#avoid_loading_into_multiple_contexts)  
  
- [Vermeiden des Ladens von mehreren Versionen einer Assembly in denselben Kontext](#avoid_loading_multiple_versions)  
  
- [Ziehen Sie in Erwägung, zum Standard-Load-Kontext zu wechseln](#switch_to_default)  
  
 In der ersten Empfehlung, [Vor- und Nachteile von Load-Kontexten](#load_contexts), erhalten Sie Hintergrundinformationen zu den anderen Empfehlungen, da diese alle eine Kenntnis von Load-Kontexten voraussetzen.  
  
<a name="load_contexts"></a>

## <a name="understand-the-advantages-and-disadvantages-of-load-contexts"></a>Vor- und Nachteile von Load-Kontexten  

 Assemblys können innerhalb einer Anwendungsdomäne in einen von drei Kontexten geladen werden. Alternativ können sie auch ohne Kontext geladen werden:  
  
- Der Standard-Load-Kontext enthält Assemblys, die beim Durchsuchen des globalen Assemblycaches, des Hostassemblyspeichers (wenn die Runtime gehostet wird, z.B. in SQL Server) und der Eigenschaften <xref:System.AppDomainSetup.ApplicationBase%2A> und <xref:System.AppDomainSetup.PrivateBinPath%2A> der Anwendungsdomäne gefunden wurden. Die meisten Überladungen der Methode <xref:System.Reflection.Assembly.Load%2A> laden Assemblys in diesen Kontext.  
  
- Der LoadFrom-Kontext enthält Assemblys, die von Speicherorten geladen werden, die vom Ladeprogramm nicht durchsucht wurden. Add-Ins können z.B. in einem Verzeichnis installiert sein, dass sich nicht im Anwendungspfad befindet. <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>, <xref:System.AppDomain.CreateInstanceFrom%2A?displayProperty=nameWithType> und <xref:System.AppDomain.ExecuteAssembly%2A?displayProperty=nameWithType> sind Beispiel für Methoden, die anhand des Pfads laden.  
  
- Der ReflectionOnly-Kontext enthält Assemblys, die mit den Methoden <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> und <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> geladen wurden. Code, der sich in diesem Kontext befindet, kann nicht ausgeführt werden. Deshalb wird darauf hier nicht weiter eingegangen. Weitere Informationen finden Sie unter [Vorgehensweise: Laden von Assemblys in den reflexionsbezogenen Kontext](../reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).  
  
- Wenn Sie eine vorübergehende dynamische Assembly mit der Reflektionsausgabe erstellt haben, befindet die Assembly sich in keinem Kontext. Außerdem werden Assemblys, die mit der <xref:System.Reflection.Assembly.LoadFile%2A>-Methode geladen wurden, ohne Kontext geladen. Assemblys, die aus Bytearrays geladen werden, werden ohne Kontext geladen, es sei denn, ihre Identität (nachdem eine Richtlinie angewendet wurde) gibt an, dass sie sich im globalen Assemblycache befinden.  
  
 Der Ausführungskontexte haben Vor- und Nachteile, wie in den folgenden Abschnitten beschrieben.  
  
### <a name="default-load-context"></a>Standard-Load-Kontext  

 Wenn Assemblys in den Load-Kontext geladen werden, werden ihre Abhängigkeiten automatisch mitgeladen. Abhängigkeiten, die in den Standard-Load-Kontext geladen werden, werden automatisch für Assemblys im Standard-Load-Kontext oder dem LoadFrom-Kontext geladen. Das Laden anhand der Assemblyidentität erhöht die Stabilität Ihrer Anwendung, da sichergestellt wird, dass unbekannte Assemblyversionen nicht verwendet werden (weitere Informationen im Abschnitt [Vermeiden von Bindungen bei partiellen Assemblynamen](#avoid_partial_names)).  
  
 Das Verwenden des Standard-Load-Kontexts hat folgende Nachteile:  
  
- Abhängigkeiten, die in die andere Kontexte geladen werden, stehen nicht zur Verfügung.  
  
- Sie können keine Assemblys von Speicherorten in den Standard-Load-Kontext laden, die sich außerhalb des Suchpfads befindet.  
  
### <a name="load-from-context"></a>LoadFrom-Kontext  

 Im LoadFrom-Kontext können Sie eine Assembly aus einem Pfad laden, der sich nicht im Anwendungspfad befindet und deshalb bei der Suche nicht berücksichtigt wird. So können Abhängigkeiten in diesem Pfad gefunden und geladen werden, da die Pfadinformationen vom Kontext verwaltet werden. Des Weiteren können Assemblys in diesem Kontext Abhängigkeiten verwenden, die in den Standard-Load-Kontext geladen wurden.  
  
 Das Laden von Assemblys mit der <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>-Methode oder einer der anderen Methoden, die anhand des Pfads laden, hat folgende Nachteile:  
  
- Wenn eine Assembly mit der gleichen Identität bereits im LoadFrom-Kontext geladen wurde, gibt <xref:System.Reflection.Assembly.LoadFrom%2A> die geladene Assembly zurück, auch wenn ein anderer Pfad angegeben wurde.  
  
- Wenn eine Assembly mit <xref:System.Reflection.Assembly.LoadFrom%2A> geladen wird und eine Assembly im Standard-Load-Kontext zu einem späteren Zeitpunkt versucht, dieselbe Assembly anhand des Anzeigenamens zu laden, schlägt der Ladeversuch fehl. Dies kann auftreten, wenn eine Assembly deserialisiert ist.  
  
- Wenn eine Assembly mit <xref:System.Reflection.Assembly.LoadFrom%2A> geladen wurde und der Suchpfad eine Assembly mit der gleichen Identität an einem anderen Speicherort enthält, kann eine <xref:System.InvalidCastException>, <xref:System.MissingMethodException> oder ein anderes unerwartetes Verhalten auftreten.  
  
- <xref:System.Reflection.Assembly.LoadFrom%2A> fordert <xref:System.Security.Permissions.FileIOPermissionAccess.Read?displayProperty=nameWithType> und <xref:System.Security.Permissions.FileIOPermissionAccess.PathDiscovery?displayProperty=nameWithType> oder <xref:System.Net.WebPermission> im angegebenen Pfad.  
  
- Wenn für die Assembly ein natives Image vorhanden ist, wird sie nicht verwendet.  
  
- Die Assembly kann nicht als domänenneutral geladen werden.  
  
- In .NET Framework Version 1.0 und 1.1 wird die Richtlinie nicht angewendet.  
  
### <a name="no-context"></a>Kein Kontext  

 Das Laden ohne Kontext ist die einzige Möglichkeit für vorübergehende, durch die Reflektionsausgabe generierte Assemblys. Das Laden ohne Kontext ist die einzige Möglichkeit, mehrere Assemblys mit der gleichen Identität in eine Anwendungsdomäne zu laden. Der Suchaufwand wird umgangen.  
  
 Aus Bytearrays geladenen Assemblys werden ohne Kontext geladen, es sei denn, die Identität der Assembly, die festgelegt wird, wenn die Richtlinie angewendet wird, entspricht der Identität der Assembly im globalen Assemblycache. In einem derartigen Fall wird die Assembly aus dem globalen Assemblycache geladen.  
  
 Das Laden ohne Kontext hat folgende Nachteile:  
  
- Es können keine anderen Assemblys an Assemblys gebunden werden, die ohne Kontext geladen wurden, es sei denn, sie behandeln das <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>-Ereignis.  
  
- Abhängigkeiten werden nicht automatisch geladen. Sie können sie vorab ohne Kontext oder in den Standard-Load-Kontext laden. Zudem können Sie sie laden, indem Sie das <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>-Ereignis behandeln.  
  
- Das Laden mehrerer Assemblys mit der gleichen Identität ohne Kontext kann zu Probleme mit der Typidentität führen. Diese ähneln den Problemen, die durch das Laden von Assemblys mit der gleichen Identität in mehreren Kontexten verursacht werden. Weitere Informationen finden Sie unter [Vermeiden des Ladens von Assemblys in mehrere Kontexte](#avoid_loading_into_multiple_contexts).  
  
- Wenn für die Assembly ein natives Image vorhanden ist, wird sie nicht verwendet.  
  
- Die Assembly kann nicht als domänenneutral geladen werden.  
  
- In .NET Framework Version 1.0 und 1.1 wird die Richtlinie nicht angewendet.  
  
<a name="avoid_partial_names"></a>

## <a name="avoid-binding-on-partial-assembly-names"></a>Vermeiden von Bindungen bei partiellen Assemblynamen  

 Die partielle Namensbindung tritt auf, wenn Sie beim Laden einer Assembly nur einen Teil des Assemblyanzeigenamens (<xref:System.Reflection.Assembly.FullName%2A>) angeben. Unter Umständen rufen Sie z.B. die <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>-Methode nur mit dem einfachen Namen der Assembly auf und lassen dabei die Version, Kultur und das öffentliche Schlüsseltoken weg. Möglicherweise rufen Sie auch die <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>-Methode auf, die zunächst die <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>-Methode aufruft. Falls die Assembly nicht gefunden werden kann, durchsucht die Methode den globalen Assemblycache und lädt die letzte verfügbare Version der Assembly.  
  
 Die partielle Namensbindung kann zu vielen Problemen führen, u.a.:  
  
- Die <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>-Methode lädt möglicherweise eine andere Assembly mit dem gleichen einfachen Namen. Möglicherweise werden so zwei völlig verschiedene Assemblys von zwei Anwendungen im globalen Assemblycache installiert, beide mit dem einfachen Namen `GraphicsLibrary`.  
  
- Die Assembly, die tatsächlich geladen wird, ist möglicherweise nicht abwärtskompatibel. Wenn Sie z.B. die Version nicht angeben, kann dies dazu führen, dass eine deutlich spätere Version als die Version geladen wird, für die Ihr Programm eigentlich geschrieben wurde. Änderungen in der späteren Version verursachen möglicherweise Fehler in Ihrer Anwendung.  
  
- Die Assembly, die tatsächlich geladen wird, ist möglicherweise nicht aufwärtskompatibel. Ihre Anwendung kann z.B. mit der aktuellsten Version der Assembly entwickelt und geprüft worden sein, aber die partielle Bindung lädt möglicherweise eine sehr viel frühere Version, die nicht über die Funktionen verfügt,die Ihre Anwendung verwendet.  
  
- Das Installieren einer neuen Anwendung kann bereits vorhandene Anwendungen unterbrechen. Eine Anwendung, die die <xref:System.Reflection.Assembly.LoadWithPartialName%2A>-Methode verwendet, kann durch die Installation einer neueren, inkompatiblen Version einer freigegebenen Assembly unterbrochen werden.  
  
- Das unvorhergesehene Laden von Abhängigkeiten kann auftreten. Wenn Sie zwei Assemblys mit einer gemeinsamen Abhängigkeit laden, kann das Laden mit partieller Bindung dazu führen, dass eine Assembly eine Komponente verwendet, für die sie nicht entwickelt bzw. geprüft wurde.  
  
 Aufgrund der Probleme, die sie verursachen kann, wurde die <xref:System.Reflection.Assembly.LoadWithPartialName%2A>-Methode als veraltet markiert. Es wird empfohlen, dass Sie stattdessen die <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>-Methode verwenden, und dass Sie vollständige Assemblyanzeigenamen angeben. Weitere Informationen finden Sie unter [Vor- und Nachteile von Load-Kontexten](#load_contexts) und [Ziehen Sie in Erwägung, zum Standard-Load-Kontext zu wechseln](#switch_to_default).  
  
 Wenn Sie die <xref:System.Reflection.Assembly.LoadWithPartialName%2A>-Methode verwenden möchten, weil es das Laden von Assemblys erleichtert, beachten Sie, dass, wenn Sie Ihre Anwendung mit einer Fehlermeldung fehlschlagen lassen, die die fehlende Assembly identifiziert, dies sehr wahrscheinlich zu einer besseren Benutzererfahrung führt als wenn Sie automatisch eine unbekannte Version der Assembly verwenden. Dies kann zu unvorhergesehenem Verhalten und Sicherheitslücken führen.  
  
<a name="avoid_loading_into_multiple_contexts"></a>

## <a name="avoid-loading-an-assembly-into-multiple-contexts"></a>Vermeiden des Ladens von Assemblys in mehrere Kontexte  

 Das Laden einer Assembly in mehrere Kontexte kann zu Problemen mit der Typidentität führen. Wenn der gleiche Typ aus der gleichen Assembly in zwei verschiedene Kontexte geladen wurde, ist dies so, als wären zwei verschiedene Typen mit dem gleichen Namen geladen worden. Eine <xref:System.InvalidCastException> wird ausgelöst, wenn Sie versuchen, einen Typ in einen anderen umzuwandeln. Dabei wird die verwirrende Nachricht angezeigt, dass Typ `MyType` nicht in Typ `MyType` umgewandelt werden kann.  
  
 Nehmen Sie z.B. an, dass die `ICommunicate`-Schnittstelle in einer Assembly mit dem Namen `Utility` deklariert wird, auf die von Ihrem Programm sowie von anderen von Ihrem Programm geladenen Assemblys verwiesen wird. Diese andere Assembly enthält Typen, die die `ICommunicate`-Schnittstelle implementieren. So können diese von Ihrem Programm verwendet werden.  
  
 Überlegen Sie jetzt, was passiert, wenn Ihr Programm ausgeführt wird. Assemblys, auf die von Ihrem Programm verwiesen wird, werden in den Standard-Load-Kontext geladen. Wenn Sie eine Zielassembly anhand deren Identität mit der <xref:System.Reflection.Assembly.Load%2A>-Methode laden, befindet sich diese sowie ihre Abhängigkeiten im Standard-Load-Kontext. Sowohl Ihr Programm als auch die Zielassembly verwenden die gleiche `Utility`-Assembly.  
  
 Stellen Sie sich aber jetzt vor, Sie würden Ihre Zielassembly mit ihrem Dateipfad mit der <xref:System.Reflection.Assembly.LoadFile%2A>-Methode laden. Die Assembly wird ohne Kontext geladen, weshalb ihre Abhängigkeiten nicht automatisch geladen werden. Möglicherweise haben Sie einen Handler für das <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>-Ereignis, um die Abhängigkeit bereitzustellen. Unter Umständen lädt er die `Utility`-Assembly ohne Kontext mit der Methode <xref:System.Reflection.Assembly.LoadFile%2A>. Wenn Sie jetzt eine Instanz eines Typs erstellen, der in der Zielassembly enthalten ist, und versuchen, diesen einer Variablen mit dem Typ `ICommunicate` zuzuweisen, wird eine <xref:System.InvalidCastException> ausgelöst, da die Runtime die `ICommunicate`-Schnittstellen in den zwei Kopien der `Utility`-Assembly als von unterschiedlichen Typen ansieht.  
  
 Es gibt viele andere Szenarios, in denen eine Assembly in mehrere Kontexte geladen werden kann. Am besten vermeiden Sie Konflikte, indem Sie die Zielassembly in Ihrem Anwendungspfad verschieben und die <xref:System.Reflection.Assembly.Load%2A>-Methode mit dem vollständigen Anzeigenamen verwenden. Dann wird die Assembly in den Standard-Load-Kontext geladen, und beide Assemblys verwenden dieselbe `Utility`-Assembly.  
  
 Wenn die Zielassembly außerhalb Ihres Anwendungspfads bleiben muss, können Sie die <xref:System.Reflection.Assembly.LoadFrom%2A>-Methode verwenden, um sie in den LoadFrom-Kontext zu laden. Wenn die Zielassembly mit einem Verweis auf die `Utility`-Assembly der Anwendung kompiliert wurde, verwendet sie die `Utility`-Assembly, die Ihre Anwendung in den Standard-Load-Kontext geladen hat. Beachten Sie, dass Probleme auftreten können, wenn die Zielassembly eine Abhängigkeit auf einer Kopie der `Utility`-Assembly hat, die sich außerhalb des Anwendungspfads befindet. Wenn diese Assembly in den LoadFrom-Kontext geladen wird, bevor Ihre Anwendung die `Utility`-Assembly lädt, schlägt der Ladevorgang Ihrer Anwendung fehl.  
  
 Im Abschnitt [Ziehen Sie in Erwägung, zum Standard-Load-Kontext zu wechseln](#switch_to_default) werden Alternativen zum Laden von Dateipfaden erläutert, wie etwa <xref:System.Reflection.Assembly.LoadFile%2A> und <xref:System.Reflection.Assembly.LoadFrom%2A>.  
  
<a name="avoid_loading_multiple_versions"></a>

## <a name="avoid-loading-multiple-versions-of-an-assembly-into-the-same-context"></a>Vermeiden des Ladens von mehreren Versionen einer Assembly in denselben Kontext  

 Das Laden von mehreren Assemblyversionen in einen Load-Kontext kann zu Problemen mit der Typidentität führen. Wenn der gleiche Typ aus der zwei Versionen derselben Assembly geladen wurde, ist dies so, als wären zwei verschiedene Typen mit dem gleichen Namen geladen worden. Eine <xref:System.InvalidCastException> wird ausgelöst, wenn Sie versuchen, einen Typ in einen anderen umzuwandeln. Dabei wird die verwirrende Nachricht angezeigt, dass Typ `MyType` nicht in Typ `MyType` umgewandelt werden kann.  
  
 Ihr Programm lädt z.B. möglicherweise eine Version der `Utility`-Assembly direkt, aber zu einem späteren Zeitpunkt lädt es möglicherweise eine andere Assembly, die eine andere Version der `Utility`-Assembly lädt. Es kann auch sein, dass ein Codefehler dazu führt, dass zwei unterschiedliche Codepfade Ihrer Anwendung verschiedene Versionen einer Assembly laden.  
  
 Dieses Problem kann im Standard-Load-Kontext auftreten, wenn Sie die <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>-Methode verwenden und vollständige Assemblyanzeigenamen angeben, die verschiedene Versionsnummern enthalten. Das Problem kann bei Assemblys, die ohne Kontext geladen wurden, durch das Verwenden der <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=nameWithType>-Methode zum Laden der gleichen Assembly aus einem anderen Pfad verursacht werden. Die Runtime sieht zwei Assemblys, die aus verschiedenen Pfaden geladen wurden, als unterschiedlich an, auch wenn deren Identitäten übereinstimmen.  
  
 Neben Problemen mit der Typidentität können mehrere Versionen einer Assembly eine <xref:System.MissingMethodException> verursachen, wenn ein Typ, der aus einer Version der Assembly geladen wird, an Code übergeben wird, der diesen Typ einer anderen Version erwartet. Der Code erwartet z.B. möglicherweise eine Methode, die in einer späteren Version hinzugefügt wurde.  
  
 Geringfügigere Fehler können auftreten, wenn das Verhalten des Typs von einer Version zur anderen geändert wurde. Eine Methode kann z.B. eine unerwartete Ausnahme auslösen oder einen unerwarteten Wert zurückgeben.  
  
 Überprüfen Sie Ihren Code gründlich, um sicherzustellen, dass nur eine Version einer Assembly geladen wird. Sie können die <xref:System.AppDomain.GetAssemblies%2A?displayProperty=nameWithType>-Methode verwenden, um zu bestimmten, welche Assemblys zu einem gegebenen Zeitpunkt geladen werden.  
  
<a name="switch_to_default"></a>

## <a name="consider-switching-to-the-default-load-context"></a>Ziehen Sie in Erwägung, zum Standard-Load-Kontext zu wechseln  

 Schauen Sie sich die Muster Ihrer Anwendung zum Laden und Bereitstellen von Assemblys an. Können Sie aus Bytearrays geladene Assemblys beseitigen? Können Sie Assemblys in den Suchpfad verschieben? Wenn sich Assemblys im globalen Assemblycache oder im Suchpfad der Anwendungsdomäne befinden (d.h. deren <xref:System.AppDomainSetup.ApplicationBase%2A> und <xref:System.AppDomainSetup.PrivateBinPath%2A>), können Sie die Assembly anhand ihrer Identität laden.  
  
 Wenn Sie Ihre Assemblys nicht alle in den Suchpfad verschieben können, ziehen Sie Alternativen wie das Add-In-Modell von .NET Framework, das Platzieren von Assemblys in den globalen Assemblycache oder das Erstellen einer Anwendungsdomäne in Erwägung.  
  
### <a name="consider-using-the-net-framework-add-in-model"></a>Ziehen Sie in Erwägung das Add-In-Modell von .NET Framework zu verwenden  

 Wenn Sie den LoadFrom-Kontext verwenden, um Add-Ins zu implementieren, die für gewöhnlich nicht in der Anwendungsbasis installiert sind, verwenden Sie das Add-In-Modell von .NET Framework. Dieses Modell ermöglicht die Isolation auf der Anwendungsdomänen- oder Prozessebene, ohne dass Sie die Anwendungsdomäne selbst verwalten müssen. Weiter Informationen zum Add-In-Modell finden Sie unter [Add-ins and Extensibility (Add-Ins und Erweiterbarkeit)](/previous-versions/dotnet/netframework-4.0/bb384200(v=vs.100)).  
  
### <a name="consider-using-the-global-assembly-cache"></a>Ziehen Sie in Erwägung, den globalen Assemblycache zu verwenden  

 Platzieren Sie Assemblys in den globalen Assemblycache, um vom Pfad der freigegebenen Assembly zu profitieren, die sich außerhalb der Anwendungsbasis befindet. Dabei büßen Sie aber nichts an den Vorteilen des Standard-Load-Kontexts ein. Ebenso wenig müssen Sie sich mit den Nachteilen der anderen Kontexte auseinandersetzen.  
  
### <a name="consider-using-application-domains"></a>Ziehen Sie in Erwägung, Anwendungsdomänen zu verwenden  

 Wenn Sie bestimmen, dass einige Assemblys nicht im Suchpfad der Anwendung bereitgestellt werden können, ziehen Sie in Erwägung, eine neue Anwendungsdomäne für diese Assemblys zu erstellen. Verwenden Sie <xref:System.AppDomainSetup>, um neue Anwendungsdomänen zu erstellen, und verwenden Sie die <xref:System.AppDomainSetup.ApplicationBase%2A?displayProperty=nameWithType>-Eigenschaft, um den Pfad anzugeben, der die Assembly enthält, die Sie laden möchten. Wenn Sie mehrere Verzeichnisse durchsuchen müssen, können Sie <xref:System.AppDomainSetup.ApplicationBase%2A> auf ein Stammverzeichnis festlegen und die <xref:System.AppDomainSetup.PrivateBinPath%2A?displayProperty=nameWithType>-Eigenschaft verwenden, um die zu durchsuchenden Unterverzeichnisse zu identifizieren. Alternativ können Sie auch mehrere Anwendungsdomänen erstellen und <xref:System.AppDomainSetup.ApplicationBase%2A> jeder Anwendungsdomäne auf den entsprechenden Pfad für deren Assemblys festlegen.  
  
 Beachten Sie, dass Sie diese Assemblys mit der <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>-Methode laden können. Da sie sich nun im Suchpfad befinden, werden sie in den Standard-Load-Kontext geladen statt in den LoadFrom-Kontext. Es wird allerdings empfohlen, dass Sie zur <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>-Methode wechseln und vollständige Assemblyanzeigenamen angeben, um sicherzustellen, dass immer die korrekten Versionen verwendet werden.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=nameWithType>
- <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>
