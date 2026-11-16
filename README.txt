Librairie en ligne de Sousse - VERSION RÉFÉRENCÉE (corrigé SEO), avec panier et administration

PAGES
  index.html, produits.html, blog.html, a-propos.html, contact.html
  panier.html  : panier et validation de la commande (paiement à la livraison)
  admin.html   : espace administrateur (commandes, messages, produits avec photos)
               accessible par le lien « Administration » en bas de chaque page

DOSSIERS
  css/       feuille de style
  js/        config.js (à remplir), db.js, panier.js, produits.js, panier-page.js, contact.js, admin.js
  images/    illustrations ; images/produits/ pour vos photos réelles
  supabase/  schema.sql : tables, règles de sécurité, stockage des photos, produits de départ

METTRE EN MARCHE (sans Supabase)
  Le catalogue, le panier et les pages s'affichent sans configuration.
  Pour la commande, le formulaire de contact et l'administration, il faut Supabase.

RELIER LE SITE À SUPABASE
  1. Créer un projet sur supabase.com.
  2. Ouvrir l'éditeur SQL, coller le contenu de supabase/schema.sql, cliquer sur Run.
  3. Authentication > Users > Add user : créer le compte administrateur (email + mot de passe).
  4. Dans l'éditeur SQL, exécuter (avec votre email) :
       insert into admins (user_id) select id from auth.users where email = 'VOTRE-EMAIL';
  5. Paramètres du projet > API : copier l'URL du projet et la clé PUBLIQUE dans js/config.js.
     Ne jamais utiliser la clé secrète (service_role).
  6. Ouvrir le site avec une adresse http : extension « Live Server » de Visual Studio Code,
     ou site publié (par exemple Netlify Drop). Le panier fonctionne mal avec un simple double-clic
     sur le fichier, car chaque navigateur gère différemment le stockage des fichiers locaux.

PHOTOS RÉELLES
  Voir images/produits/LISEZ-MOI.txt. Depuis admin.html, onglet Produits, vous pouvez envoyer
  une photo pour chaque produit.

EN CAS DE PROBLÈME
  - « supabase is not defined » : la bibliothèque (CDN) doit être chargée avant js/db.js.
  - Liste vide ou erreur de sécurité : relancer supabase/schema.sql et vérifier js/config.js.
  - Admin refusé : vérifier que le compte figure dans la table admins.
  - Envoi de photo impossible : vérifier le bucket « produits » dans Storage.

Contenu fictif : prix, coordonnées et textes sont des exemples à adapter.
Cette version est le CORRIGÉ : tout le référencement du cours y est appliqué (voir ci-dessous).
panier.html et admin.html restent en noindex.


RÉFÉRENCEMENT APPLIQUÉ (corrigé)
  - Titres uniques de 50 à 60 caractères et meta descriptions uniques de 140 à 160 caractères sur les 5 pages publiques.
  - Un seul H1 par page, hiérarchie H1 > H2 > H3 sans saut ; noms de produits en H2.
  - Texte alt sur toutes les images ; fichiers renommés (manuels-scolaires.svg, pile-de-livres.svg, etc.).
  - Ancres descriptives à la place de « Cliquez ici » ; liens internes entre toutes les pages.
  - Article de blog d'environ 280 mots, avec 4 liens internes et 1 lien externe (site du ministère de l'Éducation).
  - Balise canonical, balises Open Graph, icône du site, données structurées JSON-LD (BookStore, produits, article).
  - robots.txt, sitemap.xml (5 pages) et 404.html. panier.html et admin.html : noindex, absents du sitemap,
    et non bloqués dans robots.txt (sinon le moteur ne verrait pas la balise noindex).

À FAIRE AVANT LA PUBLICATION
  1. Remplacer VOTRE-SITE par l'adresse réelle du site dans tout le dossier
     (Visual Studio Code : Ctrl+Maj+H, « Remplacer dans les fichiers ») : canonical, Open Graph,
     JSON-LD, robots.txt et sitemap.xml.
  2. Vérifier que le lien externe de l'article (https://www.education.gov.tn/) s'ouvre bien, ou le remplacer.
  3. Remplacer les liens # des réseaux sociaux (contact.html) et les coordonnées fictives.
  4. Mesurer avec PageSpeed Insights et ajouter le site dans Google Search Console (envoyer le sitemap).
Les prix, dates et coordonnées sont fictifs.
