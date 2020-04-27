---
title: Anwendungsdomänen
ms.date: 03/30/2017
helpviewer_keywords:
- process boundaries for isolation
- application isolation
- application domains, about
- common language runtime, application domains
- application domains
- runtime, application domains
- isolation between applications
- code, verification process
- verification testing code
ms.assetid: 113a8bbf-6875-4a72-a49d-ca2d92e19cc8
ms.openlocfilehash: a5c9f4248e060d231941269f39cadbc7147ce27f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400908"
---
# <a name="application-domains"></a>Anwendungsdomänen

Betriebssysteme und Laufzeitumgebungen sorgen i. d. R. für eine gewisse Isolierung der Anwendungen voneinander. Windows verwendet beispielsweise Prozesse, um Anwendungen zu isolieren. Diese Isolierung ist erforderlich, um sicherzustellen, dass der in einer Anwendung ausgeführte Code andere, unabhängig davon ausgeführte Anwendungen nicht beeinträchtigt.  
  
 Anwendungsdomänen stellen eine Isolationsbegrenzung aus Gründen der Sicherheit, Zuverlässigkeit und Versionszuweisung sowie zum Entladen von Assemblys bereit. Anwendungsdomänen werden meist von Laufzeithosts erstellt, die vor dem Ausführen einer Anwendung als Bootstrapper für die Common Language Runtime fungieren.  
  
## <a name="the-benefits-of-isolating-applications"></a>Vorteile der Isolation von Anwendungen

 Traditionell werden auf dem gleichen Computer ausgeführte Anwendungen durch Prozessgrenzen isoliert. Jede Anwendung wird in einen eigenen Prozess geladen, wodurch die Anwendung von anderen auf dem gleichen Computer ausgeführten Anwendungen isoliert wird.  
  
 Die Anwendungen sind isoliert, da Speicheradressen prozessabhängig sind. Ein von einem Prozess an einen anderen Prozess übergebener Speicherzeiger kann im Zielprozess nicht sinnvoll verwendet werden. Außerdem können Sie keine direkten Aufrufe zwischen zwei Prozessen durchführen. Stattdessen müssen Sie Proxys verwenden, die eine Dereferenzierungsebene bieten.  
  
 Verwalteter Code muss einen Überprüfungsvorgang durchlaufen, bevor er ausgeführt werden kann (sofern der Administrator nicht eine Berechtigung zum Überspringen der Überprüfung erteilt hat). Während des Überprüfungsvorgang wird ermittelt, ob Code Zugriffsversuche auf ungültige Speicheradressen oder andere Aktionen ausführen kann, durch die der Prozess, in dem er ausgeführt wird, nicht richtig ausgeführt werden könnte. Code, der die Überprüfung bestanden hat, gilt als typsicher. Durch die Möglichkeit, Code auf Typsicherheit zu prüfen, bietet die Common Language Runtime den gleichen Grad der Isolierung wie Prozessgrenzen bei geringeren Leistungseinbußen.  
  
 Anwendungsdomänen bieten eine sicherere und flexiblere Verarbeitungseinheit, mit der die Common Language Runtime Anwendungen isolieren kann. Sie können mehrere Anwendungsdomänen in einem Prozess ausführen und dabei ohne den Mehraufwand durch prozessübergreifende Aufrufe oder das Umschalten zwischen Prozessen die gleiche Isolierung gewährleisten wie beim Ausführen in getrennten Prozessen. Durch das Ausführen mehrerer Anwendungen in einem einzelnen Prozess wird die Skalierbarkeit des Servers erheblich erhöht.  
  
 Das Isolieren von Anwendungen ist auch für die Anwendungssicherheit wichtig. Sie können z. B. Steuerelemente aus unterschiedlichen Webanwendungen in einem einzelnen Browserprozess ausführen, wobei die Steuerelemente nicht auf die Daten und Ressourcen der jeweils anderen Steuerelemente zugreifen können.  
  
 Die Isolierung durch Anwendungsdomänen bietet folgende Vorteile:  
  
- Fehler in einer Anwendung haben keine Auswirkungen auf andere Anwendungen. Da typsicherer Code keine Speicherfehler verursacht, ist bei der Verwendung von Anwendungsdomänen sichergestellt, dass der in einer Domäne ausgeführte Code keine anderen Anwendungen in dem Prozess beeinflussen kann.  
  
- Einzelne Anwendungen können beendet werden, ohne den gesamten Prozess zu beenden. Mit Anwendungsdomänen können Sie den in einer Anwendung ausgeführten Code entladen.  
  
    > [!NOTE]
    > Einzelne Assemblys oder Typen können nicht entladen werden. Es können nur vollständige Domänen entladen werden.  
  
- Der in einer Anwendung ausgeführte Code kann nicht direkt auf Code oder Ressourcen anderer Anwendungen zugreifen. Die Common Language Runtime stellt diese Isolierung sicher, indem direkte Aufrufe zwischen Objekten unterschiedlicher Anwendungsdomänen verhindert werden. Zwischen Domänen übergebene Objekte werden kopiert, oder der Zugriff erfolgt über einen Proxy. Wenn das Objekt kopiert wird, erfolgen die Aufrufe des Objekts lokal. Das heißt, dass der Aufrufer und das Objekt, auf das verwiesen wird, zur gleichen Anwendungsdomäne gehören. Wenn auf das Objekt über einen Proxy zugegriffen wird, erfolgt der Aufruf des Objekts remote. In diesem Fall befinden sich der Aufrufer und das Objekt, auf das verwiesen wird, in unterschiedlichen Anwendungsdomänen. Bei domänenübergreifenden Aufrufen wird die gleiche Infrastruktur für Remoteaufrufe verwendet wie bei Aufrufen zwischen Prozessen oder Computern. Daher müssen die Metadaten zu dem Objekt, auf das verwiesen wird, für beide Anwendungsdomänen verfügbar sein, damit die JIT-Kompilierung des Methodenaufrufs ordnungsgemäß durchgeführt werden kann. Wenn die aufrufende Domäne nicht über Zugriff auf die Metadaten des aufgerufenen Objekts verfügt, kann die Kompilierung mit einer Ausnahme vom Typ <xref:System.IO.FileNotFoundException> fehlschlagen. Weitere Informationen finden Sie unter [Remote Objects](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100)). Der Mechanismus, mit dem ermittelt wird, wie domänenübergreifend auf Objekte zugegriffen werden kann, wird durch das Objekt bestimmt. Weitere Informationen finden Sie unter <xref:System.MarshalByRefObject?displayProperty=nameWithType>.  
  
- Das Verhalten von Code wird durch die Anwendung beschränkt, in der er ausgeführt wird. Die Anwendungsdomäne stellt Konfigurationseinstellungen bereit, z. B. Richtlinien der Anwendungsversion, den Speicherort von Remoteassemblys, auf die zugegriffen wird, sowie Informationen zum Suchen von Assemblys, die in die Domäne geladen werden.  
  
- Berechtigungen für Code können durch die Anwendungsdomäne gesteuert werden, in der dieser ausgeführt wird.  
  
## <a name="application-domains-and-assemblies"></a>Anwendungsdomänen und Assemblys

 In diesem Abschnitt wird die Beziehung zwischen Anwendungsdomänen und Assemblys beschrieben. Sie müssen eine Assembly in eine Anwendungsdomäne laden, bevor Sie den darin enthaltenen Code ausführen können. Durch das Ausführen einer typischen Anwendung werden mehrere Assemblys in eine Anwendungsdomäne geladen.  
  
 Die Art und Weise, wie eine Assembly geladen wird, legt fest, ob der zugehörige JIT-kompilierte (Just-In-Time) Code von mehreren Anwendungsdomänen im Prozess gemeinsam genutzt und ob die Assembly aus dem Prozess entladen werden kann.  
  
- Wird eine Assembly domänenneutral geladen, können alle Anwendungsdomänen, die dieselbe Sicherheitsberechtigung gemeinsam nutzen, auch denselben JIT-kompilierten Code verwenden. Dadurch wird der von der Anwendung benötigte Speicher reduziert. Die Assembly kann jedoch nie aus dem Prozess entladen werden.  
  
- Wird eine Assembly nicht domänenneutral geladen, muss sie in jeder Anwendungsdomäne, in die sie geladen wird, JIT-kompiliert werden. Die Assembly kann jedoch aus dem Prozess entladen werden, indem alle Anwendungsdomänen entladen werden, in denen die Assembly geladen ist.  
  
 Der Laufzeithost legt beim Laden der Common Language Runtime in einen Prozess fest, ob Assemblys als domänenneutral geladen werden. Wenden Sie für verwaltete Anwendungen das <xref:System.LoaderOptimizationAttribute>-Attribut auf die Einstiegspunktmethode für den Prozess an, und geben Sie einen Wert aus der dazugehörigen <xref:System.LoaderOptimization>-Enumeration an. Geben Sie für nicht verwaltete Anwendungen, in denen sich die Common Language Runtime befindet, beim Aufrufen der [CorBindToRuntimeEx](../unmanaged-api/hosting/corbindtoruntimeex-function.md)-Methode das entsprechende Flag an.  
  
 Es gibt drei Möglichkeiten für das Laden domänenneutraler Assemblys:  
  
- <xref:System.LoaderOptimization.SingleDomain?displayProperty=nameWithType> – Es werden keine Assemblys als domänenneutral geladen, mit Ausnahme von Mscorlib, die immer domänenneutral geladen wird. Diese Einstellung wird als Einzeldomäne bezeichnet, da sie häufig verwendet wird, wenn der Host nur eine Anwendung im Prozess ausführt.

- <xref:System.LoaderOptimization.MultiDomain?displayProperty=nameWithType> – Alle Assemblys werden als domänenneutral geladen. Verwenden Sie diese Einstellung, wenn es mehrere Anwendungsdomänen im Prozess gibt, die alle den gleichen Code ausführen.

- <xref:System.LoaderOptimization.MultiDomainHost?displayProperty=nameWithType> – Assemblys mit starkem Namen werden als domänenneutral geladen, wenn sie und alle zugehörigen Abhängigkeiten im globalen Assemblycache installiert worden sind. Andere Assemblys werden geladen und für jede Anwendungsdomäne, in der sie geladen sind, separat JIT-kompiliert und können daher aus dem Prozess entladen werden. Verwenden Sie diese Einstellung, wenn mehrere Anwendungen in demselben Prozess ausgeführt werden oder wenn es eine Mischung aus Assemblys gibt, die von vielen Anwendungsdomänen und Assemblys gemeinsam genutzt werden, die aus dem Prozess entladen werden müssen.
  
 JIT-kompilierter Code kann nicht gemeinsam von Assemblys genutzt werden, die mit der <xref:System.Reflection.Assembly.LoadFrom%2A>-Methode der <xref:System.Reflection.Assembly>-Klasse in den LoadFrom-Kontext geladen werden oder die aus Abbildern mithilfe von Überladungen der <xref:System.Reflection.Assembly.Load%2A>-Methode geladen werden, die Bytearrays angeben.  
  
 Assemblys, die mit dem [Native Image Generator (Ngen.exe)](../tools/ngen-exe-native-image-generator.md) in nativen Code kompiliert wurden, können gemeinsam von Anwendungsdomänen genutzt werden, wenn sie beim erstmaligen Laden in einen Prozess als domänenneutral geladen werden.  
  
 JIT-kompilierter Code für die Assembly, die den Anwendungseinstiegspunkt enthält, kann nur gemeinsam genutzt werden, wenn alle zugehörigen Abhängigkeiten gemeinsam genutzt werden können.  
  
 Eine domänenneutrale Assembly kann mehr als einmal JIT-kompiliert werden. Wenn sich z. B. die Sicherheitsberechtigungen von zwei Anwendungsdomänen unterscheiden, können sie nicht denselben JIT-kompilierten Code gemeinsam nutzen. Jede Kopie einer JIT-kompilierten Assembly kann jedoch mit anderen Anwendungsdomänen gemeinsam genutzt werden, die über dieselben Berechtigungen verfügen.  
  
 Bei der Entscheidung, Assemblys als domänenneutral zu laden, müssen Sie einen Kompromiss zwischen einem geringeren Speicherbedarf und anderen Leistungsfaktoren finden.  
  
- Der Zugriff auf statische Daten und Methoden erfolgt bei domänenneutralen Assemblys langsamer, weil eine Isolierung der Assemblys erforderlich ist. Jede Anwendungsdomäne, die auf die Assembly zugreift, muss über eine eigene Kopie der statischen Daten verfügen, um domänenübergreifende Verweise auf Objekte in statischen Feldern zu verhindern. Daher enthält die Laufzeit zusätzliche Logik, mit der Aufrufer an die richtige Kopie der statischen Daten oder Methoden verwiesen werden. Durch diese zusätzliche Logik wird der Aufruf verlangsamt.  
  
- Alle Abhängigkeiten einer Assembly müssen beim domänenneutralen Laden der Assembly gefunden und geladen werden, denn eine Abhängigkeit, die nicht domänenneutral geladen werden kann, verhindert das domänenneutrale Laden der Assembly.  
  
## <a name="application-domains-and-threads"></a>Anwendungsdomänen und Threads

 Eine Anwendungsdomäne bildet eine Isolationsbegrenzung aus Gründen der Sicherheit, Versionszuweisung und Zuverlässigkeit sowie zum Entladen von verwaltetem Code. Ein Thread wird vom Betriebssystem bereitgestellt und von der Common Language Runtime zum Ausführen von Code verwendet. Zur Laufzeit wird der gesamte verwaltete Code in eine Anwendungsdomäne geladen und von einem oder mehreren verwalteten Threads ausgeführt.  
  
 Es gibt keine eindeutige Korrelation zwischen Anwendungsdomänen und Threads. Es können jederzeit mehrere Threads in einer Anwendungsdomäne ausgeführt werden, wobei ein bestimmter Thread nicht auf eine einzelne Anwendungsdomäne beschränkt ist. Das heißt, dass Threads über die Grenzen von Anwendungsdomänen hinweg verwendet werden können. Es wird nicht für jede Anwendungsdomäne ein neuer Thread erstellt.  
  
 Zu jedem Zeitpunkt werden alle Threads in einer Anwendungsdomäne ausgeführt. In jeder angegebenen Anwendungsdomäne können 0 (null), ein oder mehrere Threads ausgeführt werden. Die Laufzeit verfolgt, welche Threads in welchen Anwendungsdomänen ausgeführt werden. Sie können jederzeit bestimmen, in welcher Domäne ein Thread ausgeführt wird, indem Sie die <xref:System.Threading.Thread.GetDomain%2A?displayProperty=nameWithType>-Methode aufrufen.

### <a name="application-domains-and-cultures"></a>Anwendungsdomänen und Kulturen

 Die Kultur, die durch ein <xref:System.Globalization.CultureInfo>-Objekt dargestellt wird, ist Threads zugeordnet. Sie können die dem aktuell ausgeführten Thread zugeordnete Kultur abrufen, indem Sie die <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>-Eigenschaft verwenden. Mit der <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType>-Eigenschaft können Sie die dem aktuell ausgeführten Thread zugeordnete Kultur abrufen oder festlegen. Wenn die einem Thread zugeordnete Kultur durch Verwendung der <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType>-Eigenschaft explizit festgelegt wurde, bleibt sie diesem Thread zugeordnet, wenn der Thread Anwendungsdomänengrenzen überschreitet. Andernfalls wird die Kultur, die dem Thread jeweils zugeordnet ist, durch den Wert der <xref:System.Globalization.CultureInfo.DefaultThreadCurrentCulture%2A?displayProperty=nameWithType>-Eigenschaft in der Anwendungsdomäne bestimmt, in der der Thread ausgeführt wird:  
  
- Wenn der Wert der Eigenschaft nicht `null` ist, wird die Kultur, die von der Eigenschaft zurückgegeben wird, dem Thread zugeordnet (und daher durch die <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType>-Eigenschaft und die <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>-Eigenschaft zurückgegeben).  
  
- Wenn der Wert der Eigenschaft `null` ist, wird die aktuelle Systemkultur dem Thread zugeordnet.  
  
## <a name="programming-with-application-domains"></a>Programmieren mit Anwendungsdomänen

 Anwendungsdomänen werden normalerweise programmgesteuert durch Laufzeithosts erstellt und geändert. In einigen Fällen arbeiten aber auch Anwendungsprogramme mit Anwendungsdomänen. Beispielsweise kann ein Anwendungsprogramm eine Anwendungskomponente in eine Domäne laden, um die Domäne (und die Komponente) entladen zu können, ohne dass die gesamte Anwendung angehalten werden muss.  
  
 Die <xref:System.AppDomain> ist die programmgesteuerte Schnittstelle zu Anwendungsdomänen. Diese Klasse enthält Methoden zum Erstellen und Entladen von Domänen, zum Erstellen von Instanzen von Typen in Domänen und zum Registrieren von verschiedenen Benachrichtigungen wie das Entladen von Domänen. In der folgenden Tabelle werden häufig verwendete <xref:System.AppDomain>-Methoden aufgelistet.  
  
|AppDomain-Methode|Beschreibung|  
|----------------------|-----------------|  
|<xref:System.AppDomain.CreateDomain%2A>|Erstellt eine neue Anwendungsdomäne. Es wird empfohlen, dass Sie eine Überladung dieser Methode verwenden, die ein <xref:System.AppDomainSetup>-Objekt angibt. Dies ist die bevorzugte Methode zum Festlegen der Eigenschaften einer neuen Domäne, z. B. die Anwendungsbasis oder das Stammverzeichnis für die Anwendung, des Speicherorts der Konfigurationsdatei für die Domäne und des Suchpfads, den die Common Language Runtime verwenden soll, um Assemblys in die Domäne zu laden.|  
|<xref:System.AppDomain.ExecuteAssembly%2A> und <xref:System.AppDomain.ExecuteAssemblyByName%2A>|Führt eine Assembly in der Anwendungsdomäne aus. Hierbei handelt es sich um eine Instanzmethode, mit der Code in einer anderen Anwendungsdomäne ausgeführt werden kann, für die ein Verweis vorhanden ist.|  
|<xref:System.AppDomain.CreateInstanceAndUnwrap%2A>|Erstellt eine Instanz eines angegebenen Typs in der Anwendungsdomäne und gibt einen Proxy zurück. Verwenden Sie diese Methode, um das Laden der Assembly, die den erstellten Typ enthält, in die aufrufende Assembly zu vermeiden.|  
|<xref:System.AppDomain.Unload%2A>|Fährt die Domäne ordnungsgemäß herunter. Die Anwendungsdomäne wird erst entladen, wenn alle in der Domäne ausgeführten Threads beendet wurden oder nicht mehr in der Domäne ausgeführt werden.|  
  
> [!NOTE]
> Die Common Language Runtime unterstützt keine Serialisierung der globalen Methoden. Daher können Delegaten nicht verwendet werden, um globale Methoden in anderen Anwendungsdomänen auszuführen.  
  
 Auch die in der Spezifikation zu den Hostingschnittstellen der Common Language Runtime beschriebenen nicht verwalteten Schnittstellen bieten Zugriff auf Anwendungsdomänen. Mit Schnittstellen von nicht verwaltetem Code können Laufzeithosts Anwendungsdomänen in einem Prozess erstellen und Zugriff auf diese erlangen.  
  
## <a name="the-complus_loaderoptimization-environment-variable"></a>COMPLUS_LoaderOptimization-Umgebungsvariable

 Eine Umgebungsvariable, die die Standardladeprogramm-Optimierungsrichtlinie einer ausführbaren Anwendung festgelegt.  
  
### <a name="syntax"></a>Syntax  
  
```env  
COMPLUS_LoaderOptimization = 1  
```  
  
### <a name="remarks"></a>Hinweise

 Eine typische Anwendung lädt mehrere Assemblys in eine Anwendungsdomäne, bevor der Code, den sie enthalten, ausgeführt werden kann.  
  
 Die Methode, mit der die Assembly geladen wird, bestimmt, ob ihr Just-In-Time-(JIT)-kompilierter Code von mehreren Anwendungsdomänen im Prozess gemeinsam genutzt werden kann.  
  
- Wird eine Assembly domänenneutral geladen, können alle Anwendungsdomänen, die dieselbe Sicherheitsberechtigung gemeinsam nutzen, auch denselben JIT-kompilierten Code verwenden. Dadurch wird der von der Anwendung benötigte Speicherplatz reduziert.  
  
- Wird eine Assembly nicht domänenneutral geladen, muss sie in jeder Anwendungsdomäne, in der sie geladen wird, JIT-kompiliert werden, und das Ladeprogramm darf keine internen Ressourcen über Anwendungsdomänen hinweg freigeben.  
  
 Wenn dieser Wert auf 1 gesetzt ist, zwingt das COMPLUS_LoaderOptimizations-Umgebungsflag den Laufzeithost, alle Assemblys auf nicht domänenneutrale Weise zu laden, die als SingleDomain bezeichnet wird. SingleDomain lädt keine Assemblys als domänenneutral, mit Ausnahme von Mscorlib, die immer domänenneutral geladen wird. Diese Einstellung wird als Einzeldomäne bezeichnet, da sie häufig verwendet wird, wenn der Host nur eine Anwendung im Prozess ausführt.  
  
> [!CAUTION]
> Das COMPLUS_LoaderOptimizations-Umgebungsflag wurde für die Verwendung bei Diagnosen und Testszenarien entworfen. Eine Aktivierung des Flags kann zu erheblichem Leistungsabfall führen und die Speicherauslastung erhöhen.  
  
### <a name="code-example"></a>Codebeispiel

 Durch den Anhang von `COMPLUS_LoaderOptimization=1` an den Multi-Zeichenfolgen-Wert der Umgebung im HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\services\IISADMIN-Schlüssel kann erzwungen werden, dass keine Assemblys für den IISADMIN-Dienst als domänenneutral geladen werden.  
  
```env  
Key = HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\services\IISADMIN  
Name = Environment  
Type = REG_MULTI_SZ  
Value (to append) = COMPLUS_LoaderOptimization=1  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.AppDomain?displayProperty=nameWithType>
- <xref:System.MarshalByRefObject?displayProperty=nameWithType>
- [Programmieren mit Anwendungsdomänen und Assemblys](index.md)
- [Verwenden von Anwendungsdomänen](use.md)
