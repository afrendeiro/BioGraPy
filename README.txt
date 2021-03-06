BioGraPy - Biological Graphical Library in Python
=================================================


Quick examples
------------------------------------------

Simple test

    >>> from biograpy import Panel, tracks, features
    >>> panel=Panel(fig_width=1000,fig_dpi=100)#initialize a drawer
    >>> test_track = tracks.BaseTrack(name = 'test') 

Create 5 graphicfeatures

    >>> feat1=features.Simple(name='feat1',start=100,end=756,fc='r',aplha=0.5,height=1)
    >>> feat2=features.Simple(name='feat2',start=300,end=1056,fc='pink',aplha=0.5,height=1)
    >>> feat3=features.Simple(name='feat3',start=600,end=1356,fc='y',aplha=0.5,height=1)
    >>> feat4=features.Simple(name='feat4',start=800,end=1356,fc='g',aplha=0.5,height=1)
    >>> feat5=features.Simple(name='feat5',start= 1357,end=1806,fc='b',aplha=0.5,height=1)

Add the features to the track::

    >>> test_track.append(feat1)
    >>> test_track.append(feat2)
    >>> test_track.append(feat3)
    >>> test_track.append(feat4)
    >>> test_track.append(feat5)

Add the track to the panel::

    >>> panel.add_track(test_track)

Save the drawn image in PDF format::

    >>> panel.save('test.pdf')


or in short, using default styles, and saving as PNG::

    >>> from biograpy import Panel, tracks, features
    >>> panel=Panel(fig_width=1000)#initialize a drawer
    >>> test_track = tracks.BaseTrack(features.Simple(name='feat1',start=100,end=756,),
            features.Simple(name='feat2',start=300,end=1056,),
            features.Simple(name='feat3',start=600,end=1356,),
            features.Simple(name='feat4',start=800,end=1356,),
            features.Simple(name='feat5',start= 1357,end=1806,),
            name = 'test')
    >>> panel.add_track(test_track)
    >>> panel.save('test.png')




draw a SeqRecord

    >>> from biograpy.seqrecord import SeqRecordDrawer
    >>> from Bio import SeqIO
    >>> seqrec = SeqIO.read(open('biograpy/tests/test_uniprot.xml'),'uniprot-xml')
    >>> grseqrec = SeqRecordDrawer(seqrec)
    >>> grseqrec.save('biograpy/tests/test_uniprot.svg')
