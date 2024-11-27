# Evaluating LLMs and Potential Pitfalls

Intro to AI-Driven Science on Supercomputers @ ALCF 2024

**Contact:** Marieme Ngom ([mngom@anl.gov](mailto:///mngom@anl.gov)), Bethany Lusch ([blusch@anl.gov](mailto:///blusch@anl.gov)), Sandeep Madireddy  ([smadireddy@anl.gov](mailto:///smadireddy@anl.gov)) 


[Overview of LLMs Evaluation](https://github.com/argonne-lcf/ai-science-training-series/blob/main/08_Evaluating_LLMs/LLM_Evaluation_Overview.pdf)

[Potential Pitfalls of LLMs](https://github.com/argonne-lcf/ai-science-training-series/blob/main/08_Evaluating_LLMs/LLM-Pitfalls.pdf)
    
[Link to breakout rooms forms](https://drive.google.com/drive/folders/1BN_aBlNU-7KVIcySntRtbkBXRGpkMSyz)

Other helpful links:
- [OpenAI tokenizer](https://platform.openai.com/tokenizer)
- [Chatbot Arena](https://chat.lmsys.org/)
- [Chatbot Guardrails Arena](https://huggingface.co/spaces/lighthouzai/guardrails-arena)

 
 **Homework**
 
What do you think is a particularly good use case for LLMs for science? How would you evaluate it?
Your answer does not need to be in paragraphs. When you submit your homework form, you can link to a file in your Github repo where you wrote your answer.

Solutions:

As I have learned more about LLMs throughout this course, I see them more and more as a very powerful search engine. When you provide exactly what you are looking for, you can get amazing results. So that is why I think literature review is a good way to leverage LLMs for science. 

LLMs can process and synthesize a huge amount of scientific text data with relative accuracy and very quickly. LLMs may be able to identify papers a human researcher can not find, as well as identify more quickly papers that are foundational to the area of research. 

Unfortunately this could lead to bias and the same papers to be cited over and over again, so there should absolutely still remain some human oversight to prevent this. With that said, LLM-assistance in this case can be a big asset to the researcher responsible to conducting a literature review. 

Of course, there are intrinsic and extrinsic evaluation strategies to evaluate the LLMs, like the Vendi score to assess diversity, or text summarization which can also be automated. Here are some human evaluation strategies for some of the areas of evaluation:

1. **Accuracy**: Compare LLM-generated literature summaries to expert-created summaries

2. **Efficiency**: Measure time saved compared to traditional manual literature review; evaluate the number of relevant papers identified by the LLM vs. human researchers

3. **Trustworthiness**: Check for coverage of key papers and concepts in the field

4. **Diversity,Fairness,Bias**: Assess the diversity of sources and perspectives included; examine for potential biases in paper selection or hypothesis generation

5. **Generalization**: Assess the LLM's ability to make unexpected connections between fields

6. **Coherence**: Evaluate the model's understanding of domain-specific terminology and concepts

7. **Ethics,Reproducibility**: Test consistency of literature summaries and hypotheses across multiple runs; assess the model's ability to provide traceable sources for its outputs


