<template>
  <section class="container long-text">
    <h1>Intro to Document Clustering with K-Means</h1>
    <p>
      One challenge when working with large bodies of text is applying useful classifiers or tags to the text in order to organize sets of documents.  When working with user-generated content, you can always allow users to assign such classifiers themselves, but it's difficult to strike a balance between a bloated taxonomy and an overly-restrictive set of classifiers. At either end of that spectrum, you are likely to get users who are frustrated with many or too few options.
    </p>
    <p>
      Document clustering using machine learning can be a useful solution to either assigning classifications outright, or making suggestions for end users or intermediating experts (more on these later).  This type of clustering employs a semi-supervised instance of machine learning that groups blocks of text together based on the similarity and frequency of words that occur within those documents.  I say 'semi-supervised' because the methods don't require labeled data <i>per se</i>, but in order to assess their accuracy and utility, it is helpful to have labels associated with the data, so that a domain expert can look at the clusters and assign more meaningful categories.
    </p>
    <p>
      Disclaimer: I have dabbled in machine learning but I am far from an expert in the subject. What follows is my experience using a technique called k-means clustering which is, as far as I can tell, is currently (Jun 2017) one of the most successful methods at the moment.
    </p>
    <h2>
      Overview of the process
    </h2>
    <p>
      [the creator of Node.js] said in an excellent write-up of his immersive at Google that he was a bit overwhelmed by how unstructured and taped-together a lot of of the projects were, and hoped that one day someone would do for ML what MVC did for web frameworks.  In that spirit, I've devised this text clustering process into three parts (I have no idea if this is generalizable to other forms of ML):
      <ol>
        <li><b>The Importer</b>: the thing that imports your data and readies it for modeling.</li>
        <li><b>The Modeler</b>: the thing that takes the data and forms a model.</li>
        <li><b>The Expresser</b>: The thing that interacts with your model to get some final form of output whether it be a graph, a classification, whatever.</li>
      </ol>
    </p>
    <h2>The Importer</h2>
    <p>
      One thing that has consistently surprised me about doing ML projects is how much time I spend on pre-processing my data – extracting it from my database, cleaning it up.  Part of the reason that it takes a while is that it's not often clear what data we'll end up using and the exact form it needs to be in.  Isolating this concern to a module is useful for overall organization, and it also let's you build logic around saving and loading already-processed data.
    </p>
  </section>
</template>

<script>
  export default {}
</script>
