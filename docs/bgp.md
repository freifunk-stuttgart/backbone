# Hintergründe BGP
* tinc-Backbone soll weiter laufen können
    * alles was in tinc ffsl3 ist importieren
* die tinc-Integration soll nicht zu Umwegen führen
    * von tinc ffsl3 gelernte Routen müssen schlechter sein -> AS-Path verlängern
    * AS-Path gibt es erst im BGP-Protokoll, das kennt aber keine Interfacenamen, nur Protokolle
	* separates Protokoll für den Import des ffsl3-Interfaces
    * die IPs der einzelnen Backboneteilnehmer einzeln announcen, wie das auch im tinc ist
	* lokales Protokoll localstatic das nur die IPs des Backboneteilnehmers beinhaltet
* die Backbone-IPs sollen erreicht werden
    * statisches Announcement am jeweiligen Backbonemember
* ICVPN soll tun
* einfache Einbindung von weiteren Backbonedienste mit wenig Overhead auf gemeinsam genutzten Blechen, z.B. ffs01, ffs02, ffs03
    * 1 lokales Transfernetz mit OSPF pro Blech, oder
    * Babel (bird kann nur IPv6 Babel)

