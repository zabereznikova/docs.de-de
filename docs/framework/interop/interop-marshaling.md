---
title: Interop-Marshalling
ms.date: 03/30/2017
helpviewer_keywords:
- marshaling, COM interop
- interop marshaling
- interop marshaling, about interop marshaling
ms.assetid: 115f7a2f-d422-4605-ab36-13a8dd28142a
ms.openlocfilehash: 70514811a9d236dc485f64fc34297cdb057a1512
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124277"
---
# <a name="interop-marshaling"></a>Interop-Marshalling

Das Interop-Marshalling steuert, wie Daten in Methodenargumenten und Rückgabewerten zwischen verwaltetem und nicht verwaltetem Speicher während Aufrufen übergeben werden. Interop-Marshalling ist eine Laufzeitaktivität, die vom Marshallingdienst der Common Language Runtime ausgeführt wird.

Die meisten Datentypen verfügen über gemeinsame Darstellungen im verwalteten und nicht verwalteten Speicher. Der Interop-Marshaller behandelt diese Typen für Sie. Andere Typen können im verwalteten Speicher nicht eindeutig oder gar nicht dargestellt sein.

Ein nicht eindeutiger Typ kann entweder mehrere nicht verwaltete Darstellungen besitzen, die einem einzelnen verwalteten Typ zugeordnet werden, oder ihm können Typinformationen fehlen, wie z. B. die Größe eines Arrays. Für nicht eindeutige Typen stellt der Marshaller eine Standarddarstellung und alternative Darstellungen, wenn mehrere Darstellungen vorhanden sind, bereit. Sie können explizite Anweisungen für den Marshaller angeben, wie ein nicht eindeutiger Typ zu marshallen ist.

## <a name="platform-invoke-and-com-interop-models"></a>Plattformaufruf und COM-Interop-Modelle

Die Common Language Runtime stellt zwei Mechanismen für die Interoperation mit nicht verwaltetem Code bereit:

- Plattformaufruf, wodurch verwalteter Code Funktionen aufrufen kann, die aus einer nicht verwalteten Bibliothek exportiert wurden.
- COM-Interop, wodurch verwalteter Code über Schnittstellen mit COM-Objekten (Component Object Model) interagieren kann.

Sowohl Plattformaufruf als auch COM-Interop verwenden Interop-Marshalling, um, falls erforderlich, Methodenargumente präzise zwischen Aufrufer und Aufgerufenem und umgekehrt zu verschieben. Wie die folgende Abbildung zeigt, fließt ein Methodenaufruf eines Plattformaufrufs vom verwalteten zum nicht verwalteten Code und niemals umgekehrt, es sei denn, dass [Rückruffunktionen](callback-functions.md) beteiligt sind. Obwohl Plattformaufrufe nur vom verwalteten zum nicht verwalteten Code fließen können, können Daten als Ein-oder Ausgabeparameter in beide Richtungen fließen. COM-Interop-Methodenaufrufe können in beide Richtungen fließen.

![Plattformaufruf](./media/interop-marshaling/interop-marshaling-invoke-and-com.png "Plattformaufruf- und COM-Interop-Aufruffluss")

Auf der niedrigsten Ebene verwenden beide Mechanismen denselben Interop-Marshallingdienst. Bestimmte Datentypen werden aber ausschließlich nur von COM-Interop oder von Plattformaufrufen unterstützt. Details hierzu finden Sie unter [Default Marshaling Behavior (Standardmäßiges Marshallingverhalten)](default-marshaling-behavior.md).

## <a name="marshaling-and-com-apartments"></a>Marshalling und COM-Apartments

Der Interop-Marshaller marshallt Daten zwischen dem Common Language Runtime-Heap und dem nicht verwalteten Heap. Marshalling tritt auf, wenn der Aufrufer und der Aufgerufene nicht an derselben Instanz von Daten arbeiten können. Der Interop-Marshaller ermöglicht es dem Aufrufer und dem Aufgerufenen, scheinbar an denselben Daten zu arbeiten, auch wenn sie jeweils eine eigenen Kopie der Daten besitzen.

COM verfügt ebenfalls über einen Marshaller, der Daten zwischen COM-Apartments oder verschiedenen COM-Prozessen marshallt. Beim Aufrufen zwischen verwaltetem und nicht verwaltetem Code innerhalb desselben COM-Apartments ist der Interop-Marshaller als einziger Marschaller beteiligt. Beim Aufrufen zwischen verwaltetem und nicht verwaltetem Code in einem anderen COM-Apartment oder einem anderen Prozess sind sowohl der Interop-Marshaller als auch der COM-Marschaller beteiligt.

### <a name="com-clients-and-managed-servers"></a>COM-Clients und verwaltete Server

Ein exportierter verwalteter Server mit einer vom [Assembly Registration-Tool (Regasm.exe)](../tools/regasm-exe-assembly-registration-tool.md) registrierten Typbibliothek besitzt einen auf `Both` festgelegten `ThreadingModel`-Registrierungseintrag. Dieser Wert gibt an, dass der Server in einem Singlethread-Apartment (STA) oder einem Multithread-Apartment (MTA) aktiviert werden kann. Wie in der folgenden Tabelle dargestellt, wird das Serverobjekt im selben Apartment wie sein Aufrufer erstellt.

|COM-Client|.NET-Server|Marshallinganforderungen|
|----------------|-----------------|-----------------------------|
|STA|`Both` wird STA.|Marshalling im selben Apartment.|
|MTA|`Both` wird MTA.|Marshalling im selben Apartment.|

Da Client und Server im selben Apartment sind, verarbeitet der Interop-Marshallingdienst automatisch das gesamte Daten-Marshalling. Die folgende Abbildung zeigt, wie der Interop-Marshallingdienst zwischen verwalteten und nicht verwalteten Heaps innerhalb desselben COM-artigen Apartments agiert.

![Interop-Marshalling zwischen verwalteten und nicht verwalteten Heaps](./media/interop-marshaling/interop-heaps-managed-and-unmanaged.gif "Marshallingprozess im selben Apartment.")

Wenn Sie planen, einen verwalteten Server zu exportieren, sollten Sie daran denken, dass der COM-Client das Apartment des Servers bestimmt. Ein von einem COM-Client aufgerufener und in einem MTA initialisierter verwalteter Server muss Threadsicherheit sicherstellen.

### <a name="managed-clients-and-com-servers"></a>Verwaltete Clients und COM-Server

Die Standardeinstellung für verwaltete Clientapartments ist MTA. Der Anwendungstyp des .NET-Clients kann jedoch die Standardeinstellung ändern. Angenommen, eine Visual Basic-Clientapartmenteinstellung ist STA. Sie können eine der Eigenschaften <xref:System.STAThreadAttribute?displayProperty=nameWithType>, <xref:System.MTAThreadAttribute?displayProperty=nameWithType>, <xref:System.Threading.Thread.ApartmentState%2A?displayProperty=nameWithType> oder die Eigenschaft <xref:System.Web.UI.Page.AspCompatMode%2A?displayProperty=nameWithType> verwenden, um die Apartmenteinstellung eines verwalteten Clients zu untersuchen und zu ändern.

Der Autor der Komponente legt die Threadaffinität eines COM-Servers fest. Die folgende Tabelle zeigt die Kombinationen von Apartmenteinstellungen für .NET-Clients und COM-Server. Sie zeigt außerdem die resultierenden Marshallinganforderungen für die Kombinationen.

|.NET-Client|COM-Server|Marshallinganforderungen|
|-----------------|----------------|-----------------------------|
|MTA (Standard)|MTA<br /><br /> STA|Interop-Marshalling<br /><br /> Interop- und COM-Marshalling|
|STA|MTA<br /><br /> STA|Interop- und COM-Marshalling<br /><br /> Interop-Marshalling|

Wenn ein verwalteter Client und ein nicht verwalteter Server im selben Apartment sind, verarbeitet der Interop-Marshallingdienst das gesamte Daten-Marshalling. Wenn Client und Server in unterschiedlichen Apartments initialisiert werden, ist jedoch auch COM-Marshalling erforderlich. Die folgende Abbildung zeigt die Elemente eines apartmentübergreifenden Aufrufs:

![COM-Marshalling](./media/interop-marshaling/single-process-across-multi-apartment.gif "Apartmentübergreifender Aufruf zwischen einem .NET-Client und einem COM-Objekt")

Für apartmentübergreifendes Marshalling können Sie Folgendes tun:

- Akzeptieren Sie den Mehraufwand für das apartmentübergreifende Marshalling, der sich nur bemerkbar macht, wenn viele Aufrufe vorhanden sind, die die Apartmentgrenze überschreiten. Sie müssen die Typbibliothek der COM-Komponente registrieren, damit Aufrufe erfolgreich die Apartmentgrenze überschreiten können.
- Ändern Sie den Hauptthread, indem den Clientthread auf STA oder MTA festlegen. Wenn z. B. Ihr C#-Client viele STA-COM-Komponenten aufruft, können Sie apartmentübergreifendes Marshalling vermeiden, indem Sie den Hauptthread auf STA festlegen.

    > [!NOTE]
    > Sobald der Thread eines C#-Clients auf STA festgelegt ist, erfordern Aufrufe von MTA-COM-Komponenten apartmentübergreifendes Marshalling.

Anleitungen zum expliziten Auswählen eines Apartmentmodells finden Sie unter [Managed and Unmanaged Threading (Verwaltetes und nicht verwaltetes Threading)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100)).

## <a name="marshaling-remote-calls"></a>Marshalling von Remoteaufrufen

Wie bei apartmentübergreifendem Marshalling ist bei jedem Aufruf zwischen verwaltetem und nicht verwaltetem Code COM-Marshalling beteiligt, wenn sich die Objekte in verschiedenen Prozessen befinden. Zum Beispiel:

- Ein COM-Client, der einen verwalteten Server auf einem Remotehost aufruft, verwendet verteiltes COM (DCOM).
- Ein verwalteter Client, der einen COM-Server auf einem Remotehost aufruft, verwendet DCOM.

Die folgende Abbildung zeigt, wie Interop-Marshalling und COM-Marshalling Kommunikationskanäle über Prozess- und Hostgrenzen hinweg bereitstellen:

![COM-Marshalling](./media/interop-marshaling/interop-and-com-marshaling.gif "Prozessübergreifendes Marshalling")

### <a name="preserving-identity"></a>Beibehalten der Identität

Die Common Language Runtime behält die Identität verwalteter und nicht verwalteter Verweise bei. Die folgende Abbildung zeigt den Fluss direkter, nicht verwalteter Verweise (obere Zeile) und direkter, verwalteter Verweise (untere Zeile) über Prozess- und Hostgrenzen hinweg.

![COM Callable Wrapper und Runtime Callable Wrapper](./media/interop-marshaling/interop-direct-ref-across-process.gif "Verweisübergabe über Prozess- und Hostgrenzen hinweg")

In dieser Abbildung:

- Ein nicht verwalteter Client ruft einen Verweis auf ein COM-Objekt von einem verwalteten Objekt ab, das diesen Verweis von einem Remotehost abruft. Der Remotingmechanismus ist DCOM.
- Ein verwalteter Client ruft einen Verweis auf ein verwaltetes Objekt von einem COM-Objekt ab, das diesen Verweis von einem Remotehost abruft. Der Remotingmechanismus ist DCOM.

    > [!NOTE]
    > Die exportierte Typbibliothek des verwalteten Servers muss registriert sein.

Die Anzahl der Prozessgrenzen zwischen Aufrufer und Aufgerufenem ist irrelevant. Dieselbe direkte Referenzierung tritt bei prozessinternen und -externen Aufrufen auf.

### <a name="managed-remoting"></a>Verwaltetes Remoting

Die Laufzeit bietet auch verwaltetes Remoting, das Sie zum Einrichten eines Kommunikationskanals zwischen verwalteten Objekten über Prozess- und Hostgrenzen hinweg verwenden können. Das verwaltete Remoting kann eine Firewall zwischen den kommunizierenden Komponenten unterstützen. Dies wird in der folgenden Abbildung gezeigt.

![SOAP oder TcpChannel](./media/interop-marshaling/interop-remote-soap-or-tcp.gif "Firewallübergreifende Remoteaufrufe mit SOAP oder der TcpChannel-Klasse") Firewallübergreifende Remoteaufrufe mit SOAP oder der TcpChannel-Klasse

Einige nicht verwaltete Aufrufe können durch SOAP geleitet werden, z.B. die Aufrufe zwischen Serviced Components und COM.

## <a name="related-topics"></a>Verwandte Themen

|Titel|Beschreibung|
|-----------|-----------------|
|[Default Marshaling Behavior (Standardmäßiges Marshallingverhalten)](default-marshaling-behavior.md)|Beschreibt die Regeln, die der Interop-Marshallingdienst für das Marshalling von Daten verwendet.|
|[Marshallen von Daten mit Plattformaufruf](marshaling-data-with-platform-invoke.md)|Beschreibt, wie Sie Methodenparameter deklarieren und Argumente an Funktionen übergeben, die aus nicht verwalteten Bibliotheken exportiert wurden.|
|[Marshaling Data with COM Interop (Marshallen von Daten mit COM-Interop)](marshaling-data-with-com-interop.md)|Beschreibt, wie Sie COM-Wrapper anpassen, um das Marshallingverhalten zu ändern.|
|[How to: Migrieren von verwaltetem Code DCOM zu WCF](how-to-migrate-managed-code-dcom-to-wcf.md)|Beschreibt, wie Sie von DCOM zu WCF migrieren.|
|[How to: Zuordnen von HRESULT-Werten und Ausnahmen](how-to-map-hresults-and-exceptions.md)|Beschreibt, wie Sie benutzerdefinierte Ausnahmen zu HRESULTs zuordnen, und stellt die vollständige Zuordnung von jedem HRESULT zu seiner vergleichbaren Ausnahmeklasse in .NET Framework bereit.|
|[Interoperation mit generischen Typen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229590(v=vs.100))|Beschreibt, welche Aktionen bei Verwendung von generischen Typen für COM-Interoperabilität unterstützt werden.|
|[Interoperabilität mit nicht verwaltetem Code](index.md)|Beschreibt Interoperabilitätsdienste, die von der Common Language Runtime bereitgestellt werden.|
|[Erweiterte COM-Interoperabilität](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))|Stellt Links zu weiteren Informationen über das Einbinden von COM-Komponenten in Ihre .NET Framework-Anwendung bereit.|
|[Entwurfsüberlegungen für die Interoperation](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100))|Bietet Tipps zum Schreiben integrierter COM-Komponenten.|

## <a name="reference"></a>Referenz

<xref:System.Runtime.InteropServices?displayProperty=nameWithType>
