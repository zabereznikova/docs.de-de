---
title: Automatische Skalierung in Windows Forms
ms.date: 06/15/2017
helpviewer_keywords:
- scalability [Windows Forms], automatic in Windows Forms
- Windows Forms, automatic scaling
ms.assetid: 68fad25b-afbc-44bd-8e1b-966fc43507a4
ms.openlocfilehash: 0018b9f8644ec7d222a416bb5f71a7c61671009e
ms.sourcegitcommit: c217b067985905cb21eafc5dd9a83568d7ff4e45
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2018
ms.locfileid: "36314762"
---
# <a name="automatic-scaling-in-windows-forms"></a>Automatische Skalierung in Windows Forms
Die automatische Skalierung ermöglicht, dass ein Formular und seine Steuerelemente, die auf einem Computer mit einer bestimmten Bildschirmauflösung oder Systemschriftart entworfen wurden, ordnungsgemäß auf einem anderen Computer angezeigt werden, der eine andere Bildschirmauflösung oder Systemschriftart hat. Durch sie wird sichergestellt, dass die Größen des Formulars und seiner Steuerelemente intelligent geändert werden, sodass diese sowohl auf den Computern von Benutzern als auch auf denen von anderen Entwicklern konsistent zu systemeigenen Fenstern sowie anderen Anwendungen sind. Dadurch, dass [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] die automatische Skalierung und visuelle Stile unterstützt, kann für [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]-Anwendungen im Vergleich zu systemeigenen Windows-Anwendungen ein konsistentes Aussehen und Verhalten auf dem Computer jedes Benutzers beibehalten werden.
  
In [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], Version 2.0 oder höher, funktioniert die automatische Skalierung größtenteils wie erwartet. Änderungen des Schriftartenschemas können jedoch problematisch sein. Ein Beispiel dafür, wie zum Beheben dieses Problems finden Sie unter [wie: Reagieren auf Änderungen des Schriftartenschemas in einer Windows Forms-Anwendung](how-to-respond-to-font-scheme-changes-in-a-windows-forms-application.md).
  
## <a name="need-for-automatic-scaling"></a>Erforderlich für die automatische Skalierung  
Ohne automatische Skalierung würde eine Anwendung, die für eine bestimmte Bildschirmauflösung oder Schriftart entworfen wurde, entweder zu klein oder zu groß angezeigt, wenn diese Auflösung oder Schriftart geändert wird. Wurde die Anwendung beispielsweise mit Tahoma 9 Punkt als Basis entworfen, würde sie ohne Anpassung zu klein angezeigt, wenn sie auf einem Computer ausgeführt würde, der die Systemschriftart Tahoma 12 Punkt hat. Textelemente wie Titel, Menüs, Textfeldinhalt usw. werden kleiner gerendert als andere Anwendungen. Darüber hinaus richtet sich die Größe der Benutzeroberflächenelemente, die Text enthalten, etwa die Titelleiste, Menüs und viele Steuerelemente, nach der verwendeten Schriftart. In diesem Beispiel werden diese Elemente zusätzlich relativ kleiner angezeigt.

Die gleiche Situation ergibt sich, wenn eine Anwendung für eine bestimmte Bildschirmauflösung entworfen wurde. Die häufigste Bildschirmauflösung ist 96 dpi (Dots per Inch), die entspricht 100 % Anzeige-Skalierung, aber höhere Auflösung zeigt unterstützen 125 %, 150 %, 200 % (die jeweils gleich 120, 144 und 192-DPI) und höher werden immer häufiger. Ohne Anpassung wird eine Anwendung, insbesondere eine Grafikanwendung, die für eine bestimme Auflösung entworfen wurde, entweder zu groß oder zu klein angezeigt, wenn sie mit einer anderen Auflösung ausgeführt wird.

Mit der automatischen Skalierung lassen sich diese Probleme abschwächen, indem die Größen des Formulars und seiner untergeordneten Steuerelemente entsprechend der relativen Schriftgröße oder Bildschirmauflösung geändert werden. Windows unterstützt die automatische Skalierung von Dialogfeldern durch Verwenden einer relativen Maßeinheit, die als Dialogeinheiten bezeichnet wird. Eine Dialogeinheit basiert auf der Systemschriftart, und ihre Beziehung zu Pixeln kann über die Win32 SDK-Funktion `GetDialogBaseUnits` bestimmt werden. Wenn ein Benutzer das von Windows verwendete Design ändert, werden alle Dialogfelder automatisch entsprechend angepasst. Darüber hinaus die [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] unterstützt die automatische Skalierung entweder entsprechend der Standardsystemschriftart oder der Bildschirmauflösung. Optional kann die automatische Skalierung in einer Anwendung deaktiviert werden.

## <a name="original-support-for-automatic-scaling"></a>Ursprüngliche Unterstützung für die automatische Skalierung
In den Versionen 1.0 und 1.1 von [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] wird die automatische Skalierung in einer unkomplizierten Weise unterstützt, die von der Windows-Standardschriftart abhängt, die für die Benutzeroberfläche verwendet und durch den Win32 SDK-Wert **DEFAULT_GUI_FONT** dargestellt wird. Diese Schriftart wird normalerweise nur geändert, wenn sich die Bildschirmauflösung ändert. Der folgende Mechanismus wurde verwendet, um die automatische Skalierung zu implementieren:

1. Zur Entwurfszeit wurde die <xref:System.Windows.Forms.Form.AutoScaleBaseSize%2A>-Eigenschaft (die jetzt veraltet ist) auf die Höhe und die Breite der Systemstandardschriftart des Entwicklercomputers festgelegt.

2. Zur Laufzeit wurde die Systemstandardschriftart des Benutzercomputers verwendet, um die <xref:System.Windows.Forms.Control.Font%2A>-Eigenschaft der <xref:System.Windows.Forms.Form>-Klasse zu initialisieren.

3. Vor dem Anzeigen des Formulars wurde die <xref:System.Windows.Forms.Form.ApplyAutoScaling%2A>-Methode aufgerufen, um das Formular zu skalieren. Diese Methode hat die relative Skalierungsgröße aus <xref:System.Windows.Forms.Form.AutoScaleBaseSize%2A> und <xref:System.Windows.Forms.Control.Font%2A> berechnet und dann die <xref:System.Windows.Forms.Control.Scale%2A>-Methode aufgerufen, um das Formular und dessen untergeordneten Elemente tatsächlich zu skalieren.

4. Der Wert von <xref:System.Windows.Forms.Form.AutoScaleBaseSize%2A> wurde aktualisiert, sodass nachfolgende Aufrufe von <xref:System.Windows.Forms.Form.ApplyAutoScaling%2A> die Größe des Formulars nicht zunehmend geändert haben.

Während dieser Mechanismus für die meisten Zwecke ausreichend war, brachte er folgenden Einschränkungen mit sich:

- Da die <xref:System.Windows.Forms.Form.AutoScaleBaseSize%2A> -Eigenschaft den Basisschriftgrad als ganzzahligen Werten darstellt, treten Rundungsfehler auf, die offensichtlich werden, wenn ein Formular mehrere Auflösungen durchlaufen hat.

- Automatische Skalierung war nur in der <xref:System.Windows.Forms.Form>-Klasse, nicht in der <xref:System.Windows.Forms.ContainerControl>-Klasse implementiert. Daher wurden Benutzersteuerelemente nur ordnungsgemäß skaliert, wenn das Benutzersteuerelement mit derselben Auflösung wie das Formular entworfen und zur Entwurfszeit im Formular positioniert wurde.

- Formulare und deren untergeordneten Steuerelemente konnten nur dann gleichzeitig von mehreren Entwicklern gestaltet werden, wenn die Bildschirmauflösungen ihrer Computer identisch waren. Dies bedingte außerdem, dass das Erben durch ein Formular von der Auflösung abhängig war, die dem übergeordneten Formulars zugeordnet war.

- Diese Skalierung ist nicht mit neueren Layout-Managern kompatibel, die mit [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 2.0 eingeführt wurden, z. B. <xref:System.Windows.Forms.FlowLayoutPanel> und <xref:System.Windows.Forms.TableLayoutPanel>.

- Der Mechanismus unterstützte keine Skalierung, die direkt auf der Bildschirmauflösung basiert, aber für Kompatibilität mit [!INCLUDE[compact](../../../includes/compact-md.md)] erforderlich ist.

Obwohl dieser Mechanismus in [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 2.0 aus Gründen der Abwärtskompatibilität weiterhin unterstützt wird, wurde er durch den robusteren Skalierungsmechanismus ersetzt, der nachstehend beschrieben ist. Als Folge davon sind <xref:System.Windows.Forms.Form.AutoScale%2A>, <xref:System.Windows.Forms.Form.ApplyAutoScaling%2A>, <xref:System.Windows.Forms.Form.AutoScaleBaseSize%2A> und bestimmte <xref:System.Windows.Forms.Control.Scale%2A>-Überladungen als veraltet gekennzeichnet.

> [!NOTE]
> Sie können Verweise auf diese Member problemlos löschen, wenn Sie Ihren Legacycode auf [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 2.0 aktualisieren.

## <a name="current-support-for-automatic-scaling"></a>Aktuelle Unterstützung für die automatische Skalierung
[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 2.0 umgeht frühere Beschränkungen, indem für die automatische Skalierung von Windows Forms die folgenden Änderungen eingeführt wurden:

- Die Grundunterstützung für Skalierung wurde in die <xref:System.Windows.Forms.ContainerControl>-Klasse verschoben, sodass Formulare, systemeigene zusammengesetzte Steuerelemente und Benutzersteuerelemente eine einheitliche Skalierungsunterstützung haben. Die neuen Member <xref:System.Windows.Forms.ContainerControl.AutoScaleFactor%2A>, <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A>, <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> und <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A> wurden hinzugefügt.

- Die <xref:System.Windows.Forms.Control>-Klasse hat außerdem mehrere neue Member, die ihre Mitwirkung an der Skalierung und die Unterstützung der gemischten Skalierung im selben Formular ermöglichen. Insbesondere die Member <xref:System.Windows.Forms.Control.Scale%2A>, <xref:System.Windows.Forms.Control.ScaleChildren%2A> und <xref:System.Windows.Forms.Control.GetScaledBounds%2A> unterstützen die Skalierung.

- Unterstützung für Skalierung auf Basis der Bildschirmauflösung wurde hinzugefügt, um die Unterstützung der Systemschriftarten zu ergänzen, wie dies durch die <xref:System.Windows.Forms.AutoScaleMode>-Enumeration definiert ist. Dieser Modus ist mit der automatischen Skalierung kompatibel, die von [!INCLUDE[compact](../../../includes/compact-md.md)] unterstützt wird, wodurch eine einfachere Anwendungsmigration ermöglicht wird.

- Kompatibilität mit Layout-Managern wie <xref:System.Windows.Forms.FlowLayoutPanel> und <xref:System.Windows.Forms.TableLayoutPanel> wurde der Implementierung der automatischen Skalierung hinzugefügt.

- Skalierungsfaktoren werden jetzt als Gleitkommawerte dargestellt, wozu üblicherweise die <xref:System.Drawing.SizeF>-Struktur verwendet wird, sodass Rundungsfehler so gut wie eliminiert sind.

> [!CAUTION]
> Beliebige Kombinationen aus DPI- und Schriftartskalierungsmodi werden nicht unterstützt. Obwohl Sie ein Benutzersteuerelement mithilfe eines Modus (z. B. DPI) skalieren und ohne Probleme auf einem Formular platzieren können, für das ein anderer Modus (Schriftart) verwendet wird, kann es zu unerwarteten Ergebnissen kommen, wenn Sie ein Grundformular in einem Modus mit einem abgeleiteten Formular in einem anderen Modus mischen.

### <a name="automatic-scaling-in-action"></a>Automatische Skalierung in Aktion
Windows Forms verwendet jetzt die folgende Logik, um Formulare und deren Inhalte automatisch zu skalieren:

1. Zur Entwurfszeit speichert jede <xref:System.Windows.Forms.ContainerControl>-Instanz den Skalierungsmodus und ihre aktuelle Auflösung in der <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A>- bzw. der <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A>-Eigenschaft.

2. Zur Laufzeit wird die tatsächliche Auflösung in der <xref:System.Windows.Forms.ContainerControl.CurrentAutoScaleDimensions%2A>-Eigenschaft gespeichert. Die <xref:System.Windows.Forms.ContainerControl.AutoScaleFactor%2A>-Eigenschaft berechnet dynamisch das Verhältnis zwischen der Laufzeit- und der Entwurfszeitskalierungsauflösung.

3. Wenn das Formular geladen wird und sich die Werte von <xref:System.Windows.Forms.ContainerControl.CurrentAutoScaleDimensions%2A> und <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A> unterscheiden, wird die <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>-Methode aufgerufen, um das Steuerelement und dessen untergeordneten Elemente zu skalieren. Diese Methode übergeht das Layout und ruft die <xref:System.Windows.Forms.Control.Scale%2A>-Methode auf, um die tatsächliche Skalierung auszuführen. Danach wird der Wert von <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A> aktualisiert, um weitere Skalierung zu vermeiden.

4. <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A> wird auch in den folgenden Situationen automatisch aufgerufen:

    - Als Reaktion auf das <xref:System.Windows.Forms.Control.OnFontChanged%2A>-Ereignis, wenn der Skalierungsmodus gleich <xref:System.Windows.Forms.AutoScaleMode.Font> ist.
  
    - Wenn wieder das Layout des Containersteuerelements verwendet wird und eine Änderung in der <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A>- oder der <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A>-Eigenschaft erkannt wurde.
  
    - Wenn, wie soeben erwähnt, ein übergeordnetes <xref:System.Windows.Forms.ContainerControl> skaliert wird. Jedes Containersteuerelement muss seine untergeordneten Elemente mit seinen eigenen Skalierungsfaktoren skalieren, es darf dafür nicht den Faktor seines übergeordneten Containers verwenden.

5. Untergeordnete Steuerelemente können ihr Skalierungsverhalten auf mehrere Arten ändern:

    - Die <xref:System.Windows.Forms.Control.ScaleChildren%2A>-Eigenschaft kann überschrieben werden, um zu bestimmen, ob die untergeordneten Steuerelemente skaliert werden sollen oder nicht.

    - Die <xref:System.Windows.Forms.Control.GetScaledBounds%2A>-Methode kann überschrieben werden, um die Begrenzungen für die Skalierung des Steuerelements, aber nicht die Skalierungslogik anzupassen.

    - Die <xref:System.Windows.Forms.Control.ScaleControl%2A>-Methode kann überschrieben werden, um die Skalierungslogik für das aktuelle Steuerelement zu ändern.

## <a name="see-also"></a>Siehe auch
 <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A>  
 <xref:System.Windows.Forms.Control.Scale%2A>  
 <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>  
 <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A>  
 [Rendering von Steuerelementen mit visuellen Stilen](./controls/rendering-controls-with-visual-styles.md)  
 [Gewusst wie: Verbessern der Leistung durch das Vermeiden der automatischen Skalierung](./advanced/how-to-improve-performance-by-avoiding-automatic-scaling.md)
