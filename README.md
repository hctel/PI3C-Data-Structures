---


---

<h2 id="authors">Authors:</h2>
<ul>
<li>Nikola Mitrovic</li>
<li>Sébastien Martinez</li>
</ul>
<h1 id="selection-and-insertion-sorts">1. Selection and Insertion Sorts</h1>
<h2 id="selection">1.1 Selection</h2>
<p><strong>Principe :</strong> On recherche la position de la plus petite valeur de clé et on vient échanger sa position avec le premier élément. On considère ensuite uniquement la partie du vecteur non triée et on recommence jusqu’à ce que la liste soit complètement triée.</p>
<p><img src="https://i.ibb.co/gDKzKkn/Selection-Sort.png" alt="Selection Sort"></p>
<p><strong>Complexité :</strong> O(n²) Maximum N²/2 comparaisons et N-1 échanges.</p>
<p><strong>Avantage :</strong> Le nombre d’échanges est intéressant si le temps est un argument.</p>
<h2 id="insertion">1.2 Insertion</h2>
<p><strong>Principe :</strong> On considère le vecteur en deux parties : triée et non-triée. La partie triée ne contient au départ que la première valeur du tableau. On vient prendre la première valeur de la partie non triée et l’insérer au bon endroit dans la partie triée. Cela consiste à faire une place dans la partie triée en décalant d’une position les éléments plus grands que la valeur à insérer.</p>
<p><img src="https://i.ibb.co/W2WhCzy/Insertion-Sort.png" alt="Insertion Sort"></p>
<p><strong>Complexité :</strong> O(n²)</p>
<ul>
<li>En moyenne : N²/4 comparaisons et N²/2 échanges</li>
<li>Worst case : N²/2 comparaison et N²/2 échanges</li>
<li>Best case : N comparaisons et 0 échange (si le vecteur était déjà trié)</li>
</ul>
<p><strong>Avantage :</strong> Imbattable si le vecteur est déjà trié au départ et très rapide si le vecteur à trier est partiellement trié.</p>
<h1 id="shell-sort">2. Shell Sort</h1>
<p><strong>Principe :</strong> Le tri shell se base sur le tri par insertion en essayant de minimiser son défaut de complexité <code>O(n²)</code>. Le principe sera de diviser le vecteur en <code>h sous-vecteurs</code> afin d’effectuer des tris par sélection sur des plus petites portions. Une fois les <code>h tris</code> réalisé on vient reformer le vecteur initial qui sera dans un état un peu plus trié. Comme le tri par sélection est plus efficace dans ces situations-là, on peut obtenir une complexité entre <code>O(n²)</code> et <code>O(n log²(n))</code>.</p>
<p><img src="https://i.ibb.co/jyBKKyC/Shell-sort.png" alt="enter image description here"></p>
<p><strong>Choix de la valeur h :</strong>  Habituellement, on utilise une formule pour calculer les valeurs de  <code>h</code>  des passes successives. Dans la pratique, on utilise une série de  <code>h</code>  décroissant en choisissant des valeurs qui assurent un bon brassage des données à trier. Il faut éviter 1, 2, 4, 8, 16 … ou 1, 3, 9, 27 … parce qu’avant la dernière passe, les données des deux ou trois sous-vecteurs de la passe précédente n’ont jamais été confrontées et il reste trop de désordre pour la dernière passe.</p>
<p><strong>Avantages :</strong>  Plus efficace que le tri par insertion classique.</p>
<p><strong>Inconvénients :</strong>  Algorithme plus complexe. Pas aussi efficace que d’autres méthodes de tris comme  <code>QuickSort</code>.</p>
<h1 id="heap-sort">3. Heap Sort</h1>
<p><strong>Principe :</strong>  Se base sur une vision arbre binaire du vecteur. Le premier élément du vecteur est la racine de l’arbre virtuel (indice 0). Le fils gauche se trouve à l’indice 1 et le fils droit à l’indice 2. Le fils gauche du fils gauche de la racine est en position 3 et le fils droit du fils gauche de la racine est à l’indice 4, etc. Si on prend un élément d’indice i, le fils gauche se trouve à l’indice  <code>2*i+1</code>  et le fils droit à l’indice  <code>2*i+2</code>. De même, le père de l’élément à la position i sera à la position  <code>(i-1)/2</code>  (division entière évidemment). On peut donc considérer un vecteur comme étant un arbre binaire que l’on peut parcourir en descendant ou en montant. Un Heap (tas en français) est un arbre qui respecte  <strong>une seule règle :</strong>  <code>le père est toujours plus grand que ses deux fils.</code></p>
<p>Les étapes 2 et 3 ci-dessous sont répétées jusqu’à ce que le vecteur soit complètement trié :</p>
<ol>
<li>Le tri Heap consistera à transformer le vecteur cet arbre virtuel en respectant la propriété Heap.</li>
<li>Le plus grand élément du vecteur est alors à la position 0 et on l’échange avec la dernière position du vecteur, il est à sa place.</li>
<li>Après chaque échange on restaure. Ce qui consiste à refaire respecter la propriété Heap dans notre arbre, mais sans prendre en compte le dernier élément qui lui est correctement placé. Après restauration, l’élément à l’indice 0 est le nouveau plus grand du vecteur, on l’échange avec l’avant-dernière position du vecteur et il est à sa place.</li>
</ol>
<p><img src="https://i.ibb.co/fY8rMXW/Heap-Sort.png" alt="enter image description here"></p>
<h1 id="quicksort">4. QuickSort</h1>
<p><strong>Principe :</strong>  Consiste à choisir, parmi les données à trier, une valeur pivot et à s’arranger pour organiser les données selon quelles sont plus petites ou plus grande que cette valeur. À la fin de ce processus, le tableau à trier est virtuellement divisé en deux parties, d’une part les  <code>x valeurs inférieures</code>  au pivot et d’autre part les  <code>y valeurs supérieures</code>  à ce pivot. On recommence ensuite ce processus sur les  <code>x premières valeurs</code>  (choix d’une nouvelle valeur pivot), ce qui conduira à  <em>"couper</em>" en deux ce demi-tableau et ainsi de suite jusqu’à ce que la taille du  <em>"demi-demi-…-demi-tableau</em>  ne contienne plus qu’un seul élément. On fait la même chose sur les  <code>y valeurs</code>  résultant du premier découpage. La vidéo  <a href="https://youtu.be/PgBzjlCcFvc?t=30">suivante</a>  illustre le principe.</p>
<p><strong>Avantages :</strong>  Complexité  <code>O(n log(n))</code>  ce qui est optimal pour un tri par comparaison. Dans le pire des cas, la complexité est quadratique. Efficace pour de larges quantités de données.</p>
<p><strong>Inconvénients :</strong>  Ne tire aucun avantage à ce que le vecteur soit en partie trié.</p>
<h1 id="single-linked-list">5. Single Linked List</h1>
<p><strong>Principe :</strong>  Structure de données pouvant contenir plusieurs éléments. Chaque élément possède un pointeur vers l’élément suivant. La liste est un pointeur vers le premier élément de la liste appelé  <strong>“Head”</strong>. Le dernier élément pointe vers une adresse spécifique pour signifier la fin de la liste,  <strong>“Tail”</strong>.</p>
<p><strong>Avantage :</strong>  Permet de stocker des valeurs de même type, mais a une taille variable même après création. On peut y insérer ou supprimer des éléments.</p>
<p><strong>Inconvénient :</strong></p>
<ul>
<li>À nombre d’éléments égal, une liste chaînée occupe  <strong>plus de mémoire</strong>  car elle a besoin de stocker également les pointeurs.</li>
<li>Pour accéder à un élément d’une liste chaînée, on est obligé de parcourir tous les maillons jusqu’au maillon recherché. Le  <strong>temps d’accès</strong>  est donc d’autant plus grand que l’élément recherché est loin dans la liste.</li>
</ul>
<p><strong>Ajout/suppression d’éléments :</strong><br>
On a les trois pointeurs suivants :  <code>*head</code>,  <code>*tail</code>  et  <code>*tmp</code></p>
<ol>
<li>Ajout en début de liste : on demande à  <code>*tmp</code>  de pointer au même endroit que  <code>*head</code>. Ensuite  <code>*head</code>  de pointer vers le nouvel élément et ce dernier de pointer au même endroit que  <code>*tmp</code>.<br>
<img src="https://i.ibb.co/GR8jYbB/List-add-first.png" alt="enter image description here"></li>
<li>Ajout en fin de liste : on fait pointer <code>*tail</code> vers le nouvel élément et ce dernier vers la valeur <code>NULL</code>.<br>
<img src="https://i.ibb.co/gwKxpT9/List-add-end.png" alt="enter image description here"></li>
<li>Supression en début de liste : on fait pointer <code>*head</code> vers l’élément juste après.<img src="https://i.ibb.co/wgbFWNs/List-remove-first.png" alt="enter image description here"></li>
<li>Suppression en fin de liste : comme on n’a pas de pointeur sur l’avant-dernier élément, on va devoir parcourir la liste séquentiellement jusqu’à ce que le prochain élément estsoit <code>NULL</code>. Ainsi on peut sélectionner l’avant-dernier élément et le faire pointer sur <code>NULL</code>.<br>
<img src="https://i.ibb.co/p3DDN1s/List-remove-end.png" alt="enter image description here"></li>
</ol>
<h1 id="double-linked-list-and-circular-list">6. Double Linked List and Circular List</h1>
<h2 id="double-linked-list">6.1 Double Linked List</h2>
<p><strong>Principe :</strong> Lorsque chaque élément d’une liste pointe à la fois vers l’élément suivant et précédent, nous parlons alors de liste doublement chainée.</p>
<p><img src="https://i.ibb.co/jfpvsHY/Double-linked-list.png" alt="enter image description here"></p>
<p><strong>Avantages :</strong>  L’accès peut se faire indifféremment dans les deux sens. Cela permet d’opérer une insertion avant ou après un élément, sans nécessairement disposer d’un pointeur sur un voisin, alors qu’une liste simplement chaînée n’autorise une insertion qu’à une seule position par rapport à un élément.</p>
<p><strong>Inconvénients :</strong>  Cette structure est plus coûteuse en mémoire (un pointeur supplémentaire par élément) et en nombre d’instructions pour la mise à jour : une insertion coûte quatre copies de pointeurs, contre deux dans le cas d’une liste simplement chaînée.</p>
<h2 id="circular-list">6.2 Circular List</h2>
<p><strong>Principe :</strong> Une liste cyclique (ou circulaire) est créée lorsque le dernier élément possède une référence vers le premier élément (si la liste est doublement chaînée, alors le premier élément possède aussi une référence vers le dernier). L’utilisation de ce type de liste requiert des précautions pour éviter des parcours infinis, par exemple, lors d’une recherche vaine d’élément.</p>
<p><img src="https://i.ibb.co/TTnkpK6/Circular-linked-list.png" alt="enter image description here"></p>
<h1 id="sparse-matrix">7. Sparse Matrix</h1>
<p><strong>Le problème :</strong>  Ce sont par définition de grands tableaux contenant un grand nombre de cases vides. Un problème de gaspillage de place apparait lorsque l’on essaye de regrouper un grand nombre d’informations et de catégories dans un seul tableau. Toutes les cases ne peuvent être remplies.</p>
<p><strong>Solutions :</strong></p>
<ul>
<li>Une première solution est de diviser la matrice en deux sous matrices. En effet en divisant le problème on va se retrouver avec des sous-matrices moins vides.  Une solution pas vue en cours mais très intéressante est donnée par cette <a href="https://youtu.be/V3TAtTtC4Xs?t=251">charmante indienne</a>.</li>
<li>La deuxième solution, plus complexe, est d’assigner à chaque ligne et colonne un pointeur vers une liste qui peut elle même pointer vers d’autres listes.</li>
</ul>
<h1 id="stack-and-queue">8. Stack and Queue</h1>
<p><strong>Principe :</strong> Variante des listes chainées où l’on ne peut ajouter des nouveaux éléments seulement en début ou en fin. Ils possèdent la même structure avec un pointeur vers l’élément suivant dont le dernier pointe vers <code>NULL</code>.</p>
<ul>
<li>
<p><strong>Piles (Stack) :</strong> <code>Last In First Out</code>.<br>
<img src="https://i.ibb.co/SRpYDKk/Piles.png" alt="enter image description here"><br>
<strong>Implementation :</strong><br>
<strong>Vecteur :</strong> Pour utiliser le vecteur, il faudra prévoir une case pour mémoriser l’indice de la dernière valeur de la pile. La taille de la pile doit être connue lors de la création et est donc fixe.<br>
<strong>Liste :</strong> Une liste simplement chainée dans laquelle on va ajouter/retirer en début de liste. Aucun parcours de la liste n’est nécessaire.</p>
</li>
<li>
<p><strong>Files (Queue) :</strong> <code>First In First Out</code>.<br>
<img src="https://i.ibb.co/vHYdBc4/Files.png" alt="enter image description here"><br>
<strong>Implementation :</strong><br>
<strong>Vecteur :</strong> Le vecteur doit être circulaire. Grâce aux pointeurs <code>last</code> et <code>first</code> on va pouvoir ajouter en fin et retirer en début.  La taille doit être connue lors de la création et est donc fixe.<br>
<img src="https://i.ibb.co/xfBTjyG/Implem-Vectoriel-File.png" alt="enter image description here"><br>
<strong>Liste :</strong> Une liste simplement chainée dans laquelle on va pouvoir ajouter en fin et enlever en début de liste.</p>
</li>
</ul>
<h1 id="binary-search-trees-1">9. Binary Search Trees (1)</h1>
<p><strong>Principe :</strong> Lorsqu’on construit un arbre binaire on le fait de manière à ce qu’il soit trié, sinon aucun intérêt. On insère les éléments dans l’arbre dans l’ordre dans lequel ils arrivent et lorsque la case n’est pas libre, si on est plus petit que la case on place l’élément à gauche et inversement à droite. Chaque élément a un pointeur vers ses enfants de gauche et droite. Le pointeur est <code>NULL</code> s’il n’a pas d’enfant.</p>
<p><img src="https://i.ibb.co/BKF6Ny6/Binary-Search-Tree.png" alt="enter image description here"></p>
<p><strong>Insertion d’un élément :</strong>  Comme expliqué dans le principe de fonctionnement, lorsqu’on insère un nouvel élément on vient le placer tel que si la racine est occupée, il ira à droite si &gt; root ou à gauche si &lt; root. Et si la racine est libre il prendra tout simplement sa place.</p>
<p><strong>Supression d’un élément :</strong>  Nous avons 3 situations :</p>
<ul>
<li>En bout d’arbre c’est assez facile, il suffit de modifier le pointeur du parent du dernier noeud pour pointer vers  <code>NULL</code>.<br>
<img src="https://i.ibb.co/Ycz44zP/Delete-Node.png" alt="enter image description here"></li>
<li>Si on veut effacer un noeud qui possède un seul enfant, il faudra relier cet <em>“orphelin”</em> au parent du noeud et puis supprimer ce noeud en faisant pointer son parent vers <code>NULL</code>.<br>
<img src="https://i.ibb.co/B2g5ycQ/Delete-Node-one-child.png" alt="enter image description here"></li>
<li>Si on veut effacer un noeud possédant 2 enfants, il faut dans un premier temps créer un pointeur temporaire <code>tmp</code> sur l’enfant de gauche. Ce pointeur va ensuite voyager jusqu’à pointer la valeur la plus à droite de cet enfant. On peut ensuite accrocher l’enfant de droite du noeud au pointeur <code>tmp</code> puisque les éléments à droite sont toujours plus grands que ceux à gauche. Une fois l’enfant de droite <em>“adopté”</em> on peut raccorder l’enfant de gauche au parent du noeud à supprimer. Et terminer par supprimer le noeud en faisant pointer son parent vers <code>NULL</code>.<br>
<img src="https://i.ibb.co/Db9ydSv/Delete-Node-two-children.png" alt="enter image description here"></li>
</ul>
<p><strong>Mode de parcours :</strong> on parle de parcours infixe ou encore LVR (Left Visit Right). Chaque case de l’arbre possède une sorte de sets d’action à exécuter: <code>LVR</code>. Lorsqu’on parcourt l’arbre, on commence par la racine qui a un pointeur. Prenons l’exemple suivant :</p>
<p><img src="https://i.ibb.co/fVRcGMJ/LVR.png" alt="enter image description here"></p>
<ol>
<li>On commence par l’action  <code>LEFT</code>  de la racine qui consiste à pointer l’enfant à gauche. On descend dans l’arbre en exauçant le  <code>LEFT</code>  de chaque enfant jusqu’à ce qu’on ne puisse plus aller à gauche.</li>
<li>Pour ce dernier élément le  <code>LEFT</code>  a été exécuté on peut passer à son action  <code>VISIT</code>  qui consiste à consulter la valeur de la case.</li>
<li>Ensuite on passe à l’action  <code>RIGHT</code>  consistant à pointer un enfant à droite s’il y en a bien sûr.</li>
</ol>
<p>Une fois les trois actions  <code>LVR</code>  exécuté pour l’élément le plus de l’arbre on passe à l’élément qui le précède. On peut directement passer à l’action  <code>VISIT</code>  puisque celui-ci à déjà utilisé son  <code>LEFT</code>. Il exécutera ensuite son  <code>RIGHT</code>  pour descendre dans ses enfants. Ces derniers exécuteront leur  <code>LVR</code>  jusqu’a remonter chez son parent.</p>
<p>On remonte ainsi jusqu’à la racine qui une fois “visité” passera à son  <code>RIGHT</code>  pour à son tour faire exécuter les  <code>LVR</code>  de tous ses enfants.</p>
<h1 id="binary-search-trees-2">10. Binary Search Trees (2)</h1>
<p><strong>Manipulation par rotation :</strong></p>
<ul>
<li>On peut effectuer des rotations à droite, de manière à ce que le parent (avec son enfant de droite  <code>R</code>) vienne s’accrocher à la droite de son enfant de gauche en  <code>Q</code>  sur la figure (a). Ainsi l’enfant de gauche peut prendre la place du père. Cette manière de procéder permet de garder un arbre trié.<br>
<img src="https://i.ibb.co/bKCFTDH/Rotation-droite.png" alt="enter image description here"></li>
<li>On peut effectuer des rotations à gauche en faisant l’opposé des actions décrites plus haut.</li>
</ul>
<p><strong>Déséquilibrage :</strong></p>
<ul>
<li><strong>Problème :</strong>  Lorsqu’on manipule l’arbre en y insérant/supprimant des éléments on peut introduire un déséquilibre dû au nombre de noeuds différent à gauche et à droite d’un parent.<br>
<img src="https://i.ibb.co/VDpmv1D/D-s-quilibre.png" alt="enter image description here"></li>
<li><strong>Solutions :</strong>  Il existe différentes méthodes d’équilibrage à base de rotation comme les arbres  <a href="#11-avl-trees">AVL</a></li>
</ul>
<h1 id="avl-trees">11. AVL Trees</h1>
<p><strong>Principe :</strong> c’est un algorithme qui permet de rendre un arbre équilibré en associant aux différents noeuds des niveaux de désiquilibrede l’arbre. <code>+n</code> et <code>-n</code> lors d’un déséquilibre à droite ou à gauche et <code>0</code> lorsque le noeud est équilibré. À partir d’un déséquilibre de <code>+2</code>ou <code>-2</code>, l’arbre va effectuer une rotation classique afin de rééquilibrer.</p>
<p><img src="https://i.ibb.co/JBm55Gq/AVL-Trees.png" alt="enter image description here"></p>
<p><strong>Utilité :</strong> Permet de réaliser des insertions, suppressions et recherche de complexité logarithmique O(log(n)). AVL assure un équilibrage de maximum 2 niveaux.</p>
<h1 id="data-compression">12. Data compression</h1>
<h2 id="run-length-encoding">12.1 Run-length Encoding</h2>
<p>Lorsque l’on code par plage, on va essayer de noter plusieurs caractères qui se suivent d’une manière différente.</p>
<ul>
<li>En comptant le nombre de répétitions d’un caractère, un message composé uniquement de lettre  <code>AAAABBAAACCCCCB</code>  devient  <code>4A2B3A5CB</code>. On constate un gain de place évident.</li>
<li>Si le message contient des caractères alphanumériques, on vient placer un caractère d’échappement (Escape)  <code>Z</code>  devant un chiffre pour signifier qu’il indique le nombre d’apparitions de la lettre juste à côte. Le message  <code>4AAAA5BBB</code>  devient  <code>4</code><em>Z4</em><code>A5BBB</code>. On constate avec cette méthode que si une lettre se répète moins de 3 fois, on va préférer garder la répétition.  <code>BBB</code>  n’a aucun intérêt à devenir  <code>Z3B</code>.</li>
</ul>
<h2 id="variable-length-code">12.2 Variable-length Code</h2>
<p>On va coder des caractères très fréquents sur moins de bits que des caractères plus rares. En prenant le cas du français on codera la lettre <code>E</code> sur 4 bits car très susceptible d’apparaitre et la lettre <code>Z</code> sur 13 bits, car beaucoup moins susceptibles d’apparaître. On optimise ainsi l’espace.</p>
<h1 id="absract-data-type-adt">13. Absract Data Type (ADT)</h1>
<p><strong>Définition :</strong>  L’objectif d’un type abstrait de données (TAD, ou ADT en anglais) est de cacher les détails d’implémentation de la structure de données, tout en modélisant le monde réel. Les changements d’implémentation de TAD doivent être indépendants du reste du programme, et celui-ci est autodocumenté. Les opérations réalisables avec chaque TAD sont définies dans son interface. Les noms de TAD sont représentatifs de leurs fonctionnalités ; Nous en avons déjà rencontré quelques-uns : par exemple la pile et la file qui peuvent s’implémenter de différentes façons.</p>
<p><strong>Exemples de TAD :</strong><br>
<strong>1. Deque :</strong>  Est une  <code>file</code>  à deux bouts, une séquence d’éléments à laquelle on peut ajouter et enlever aux deux extrémités. Son interface propose au minimum les méthodes suivantes :</p>
<ul>
<li>IsEmpty()</li>
<li>insertFirst(element)</li>
<li>insertLast(element)</li>
<li>removeFirst()</li>
<li>removeLast()<br>
L’implémentation peut se faire avec une liste simplement ou doublement chaînée avec pointeur de fin de liste.</li>
</ul>
<p><strong>2. Dictionnaire :</strong>  Permet, comme le map le stockage de paires clé-valeur, mais une clé peut être associée à plusieurs valeurs. Son interface propose au minimum les méthodes suivantes :</p>
<ul>
<li>Size() : nbr de paires clé-valeur</li>
<li>isEmpty() pas une seule clé-valeur</li>
<li>find(k) renvoie une valeur associée à la clé k (null si k n’existe pas dans le dictionnaire)</li>
<li>findAll(k) renvoie un itérateur sur les valeurs associées à la clé k (null si k n’existe pas dans le dictionnaire)</li>
<li>insert(k,v) ajoute la paire clé-valeur (k,v)</li>
<li>remove(k,v) supprime la clé-valeur</li>
<li>entries() est un itérateur sur les paires clé-valeurs<br>
L’implémentation peut se faire avec une liste chaînée ordonnée ou non ou une liste à saut (skipList).</li>
</ul>
<h1 id="error-detecting-codes">14. Error-Detecting Codes</h1>
<p><strong>Principe :</strong>  Afin de garantir la fiabilité des informations lors d’une transmission de données, on y introduit suffisamment de redondance par un codage de correction.</p>
<p>Le cas le plus simple est l’utilisation d’un bit de parité. On ajoute pour chaque bloc de n bits un bit qui est la somme (sans report) des bits du bloc (1+1=0). Ce système permet de détecter si un  <code>nombre impair</code>  de bit est  <code>incorrect</code>  dans le bloc. En cas de nombre pair d’erreurs, le bit de parité sera correct. Ce système consiste donc à ajouter au bloc de bits à transmettre le modulo 2 (0 ou 1) de ce bloc.</p>
<p><strong>Améliorer le nombre de détections :</strong>  Si l’on consacre 2 bits à la détection d’erreur, on peut utiliser un modulo 4 (0, 1, 2 ou 3 c.-à-d. en binaire 00, 01, 10 ou 11). Si au décodage, le modulo 4 est correct, cela signifie qu’il y a 0, 4, 8… erreurs de transmission. Le 0 étant le plus probable surtout si le bloc transmis est de petite taille.</p>
<p><strong>En cas de détection :</strong>  On peut constater que cette technique permet de détecter des erreurs, mais pas de les corriger. Si le code détecteur est assez développé il peut corriger l’erreur comme le  <code>codage de Hamming</code>. Autrement une solution plus simple consiste à demander de renvoyer le message.</p>
<h1 id="bibliography">Bibliography</h1>
<p>A. LORGE, <em>3BE Structures de données</em>, 2021<br>
A. LORGE, <a href="https://teams.microsoft.com/_#/school/files/General?threadId=19%3Adad3058aa849416991b553df80365ed6%40thread.tacv2&amp;ctx=channel&amp;context=Recordings&amp;rootfolder=%252Fsites%252F3BEPG3L-L1Projetcopier%252FDocuments%2520partages%252FGeneral%252FRecordings">Teams-Recordings</a>, 2021</p>

