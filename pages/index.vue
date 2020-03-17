<template>
  <div>
    <h1>ATTESTATION DE DÉPLACEMENT DÉROGATOIRE</h1>
    <h2>En application de l’article 1er du décret du 16 mars 2020 portant réglementation des
déplacements dans le cadre de la lutte contre la propagation du virus Covid-19 :</h2>

    <p>Je soussigné(e)</p>
    <table>
      <tr @click="demander('nom')"><th>Mme / M.</th><td><em>{{ this.nom }}</em></td></tr>
      <tr @click="demander('naissance')"><th>Né(e) le :</th><td><em>{{ this.naissance }}</em></td></tr>
      <tr @click="demander('adresse')"><th>Demeurant :</th><td><em>{{ this.adresse }}</em></td></tr>
    </table>
    <p>certifie que mon déplacement est lié au motif suivant (cocher la case) autorisé par
l’article 1<sup>er</sup> du décret du 16 mars 2020 portant réglementation des déplacements dans
le cadre de la lutte contre la propagation du virus Covid-19 :</p>
    <ul>
      <li><label for="professionnel"><input type="checkbox" id="professionnel"> déplacements entre le domicile et le lieu d’exercice de l’activité professionnelle,
lorsqu’ils sont indispensables à l’exercice d’activités ne pouvant être organisées
sous forme de télétravail (sur justificatif permanent) ou déplacements
professionnels ne pouvant être différés ;</label></li>
      <li><label for="achat"><input type="checkbox" id="achat"> déplacements pour effectuer des achats de première nécessité dans des
établissements autorisés (liste sur gouvernement.fr);</label></li>
      <li><label for="sante"><input type="checkbox" id="sante"> déplacements pour motif de santé;</label></li>
      <li><label for="famille"><input type="checkbox" id="famille"> déplacements pour motif familial impérieux, pour l’assistance aux personnes
vulnérables ou la garde d’enfants ;</label></li>
      <li><label for="sport"><input type="checkbox" id="sport"> déplacements brefs, à proximité du domicile, liés à l’activité physique individuelle
des personnes, à l’exclusion de toute pratique sportive collective, et aux besoins
des animaux de compagnie.</label></li>
    </ul>

    <p id="date" @click="demander('lieu')">Fait à <em>{{ this.lieu }}</em> le <em>{{ this.date }}</em></p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      nom: 'Faustin R Rivière',
      naissance: '12/01/1986',
      adresse: `74  rue Petite Fusterie
38300 Bourgoin-Jallieu`,
      lieu: 'Lyon',
    }
  },
  computed: {
    date: () => (new Date()).toLocaleDateString(),
  },
  methods: {
    demander(champ) {
      const valeur = prompt(`Entrez un ${champ}`, this[champ])
      if (valeur?.length > 0) {
        this[champ] = valeur
      }
    }
  }
}
</script>
