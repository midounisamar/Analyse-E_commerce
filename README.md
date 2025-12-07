<h1> Projet : Analyse Prédictive E-Commerce  RFM, Segmentation & Prédiction du Churn </h1>

 Dans le domaine du e-commerce, les entreprises disposent d'importantes quantités de données transactionnelles qu'il est essentiel d'exploiter pour mieux comprendre le comportement des clients, identifier des segments spécifiques, anticiper le churn et optimiser les actions marketing. Ce projet s’interroge sur la manière d’utiliser ces données pour segmenter efficacement la clientèle à l’aide de l’analyse RFM et du Machine Learning, prédire les clients susceptibles de churner, et visualiser les indicateurs clés de performance (KPI) via un dashboard interactif. Pour cela, les objectifs sont de réaliser une analyse RFM complète, de construire une segmentation client grâce à l’algorithme K-Means, puis de développer un modèle prédictif de churn utilisant Random Forest  , Gradient Boosting et XGBoost.






<h2> Outils et Bibliothèques Utilisés</h2>

<ul>
  <li><strong>Éditeur :</strong> VS Code avec l’extension <strong>Jupyter</strong> pour exécuter des notebooks interactifs.</li>

  <li><strong>Bibliothèques Python :</strong>
    <ul>
      <li><code>pandas</code> → manipulation des données</li>
      <li><code>numpy</code> → calculs numériques</li>
      <li><code>matplotlib</code> → visualisation graphique</li>
      <li><code>seaborn</code> → visualisations statistiques</li>
      <li><code>scikit-learn</code> → machine learning (prétraitement, modèles, métriques, clustering…)</li>
      <li><code>xgboost</code> → modèle avancé Gradient Boosting</li>
      <li><code>scipy</code> → calculs scientifiques (distances, statistiques…)</li>
    </ul>
  </li>

  <li><strong>Modèles utilisés :</strong>
    <ul>
      <li><code>GradientBoostingClassifier</code></li>
      <li><code>RandomForestClassifier</code></li>
      <li><code>XGBClassifier</code></li>
      <li><code>KMeans</code></li>
    </ul>
  </li>

  <li><strong>Évaluations :</strong>
    <ul>
      <li><code>accuracy_score</code></li>
      <li><code>recall_score</code></li>
      <li><code>f1_score</code></li>
      <li><code>confusion_matrix</code></li>
      <li><code>silhouette_score</code> → pour mesurer la qualité du clustering</li>
    </ul>
  </li>
</ul>


<h2> Les étapes de projet</h2> 

<ul>
<li>Client churn = n'a pas acheté depuis ≥ <strong>90 jours</strong>.</li>
<li>OU forte baisse de Frequency ou Monetary sur une fenêtre temporelle définie (ex: baisse > 50% sur les 3 derniers mois).</li>
</ul>


<h3>4.2 Feature Engineering</h3>
<p>Variables à construire :</p>
<ul>
<li>R, F, M (ou scores RFM)</li>
<li>Variation % de dépenses (ex: montant derniers 3 mois vs 3 mois précédents)</li>
<li>Cluster (one-hot encoded)</li>
<li>Country / Pays (encoding selon cardinalité)</li>
<li>Moyenne panier = monetary / frequency</li>
<li>Temps moyen entre achats, médiane inter-purchase interval</li>
<li>Features temporelles : jours depuis 1er achat, âge du client</li>
</ul>


<h3>4.3 Séparation Train / Test</h3>
<ul>
<li>Split temporel recommandé : utiliser une date de coupure pour éviter la fuite temporelle (ex: training jusqu'à T0, test après T0).</li>
<li>Sinon stratified split si label équilibré/déséquilibré.</li>
</ul>


<h3>4.4 Modélisation</h3>
<p>Modèles candidats :</p>
<ul>
<li>Random Forest</li>
<li>XGBoost</li>
<li>Gradient Boosting </li>
</ul>
<p>Évaluation :</p>
<ul>
<li>Accuracy</li>
<li>Recall (priorité si on veut capter churners)</li>
<li>F1-score</li>
<li>Matrice de confusion</li>
<li>Courbes ROC / PR si pertinent</li>
</ul>


<h3>4.5 Interprétation</h3>
<ul>
<li>Importance des variables (feature importance, SHAP pour explications locales/globales).</li>
<li>Analyse des faux positifs / faux négatifs et coûts associés (ex: coût d'une campagne de réactivation vs perte client).</li>
<li>Recommandations marketing basées sur le score churn (p.ex. envoyer offres d'incitation aux "à risque" ou réengagement intensif pour "can't lose them").</li>
</ul>
</section>





